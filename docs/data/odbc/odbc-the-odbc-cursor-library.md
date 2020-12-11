---
description: 了解详细信息： ODBC： ODBC 游标库
title: ODBC：ODBC 游标库
ms.date: 11/04/2016
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
ms.openlocfilehash: 1b7c05529f771b281e623502a4b8c4358e17db71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160982"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC：ODBC 游标库

本主题介绍 ODBC 游标库，并说明如何使用它。 有关详细信息，请参阅：

- [游标库和级别 1 ODBC 驱动程序](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [定位更新和时间戳列](#_core_positioned_updates_and_timestamp_columns)

- [使用游标库](#_core_using_the_cursor_library)

ODBC 游标库是 (DLL) 的动态链接库，它驻留在 ODBC 驱动程序管理器和驱动程序之间。 在 ODBC 术语中，驱动程序维护游标，以跟踪其在记录集中的位置。 光标将标记您已滚动到的记录集中的位置（当前记录）。

## <a name="cursor-library-and-level-1-odbc-drivers"></a><a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> 游标库和级别 1 ODBC 驱动程序

ODBC 游标库为第1级驱动程序提供以下新功能：

- 向前和向后滚动。 2级驱动程序不需要游标库，因为它们已经可滚动。

- 支持快照。 游标库管理包含快照记录的缓冲区。 此缓冲区反映了您的程序删除和编辑记录，而不是其他用户的添加、删除或编辑。 因此，快照的当前位置就是游标库的缓冲区。 在调用之前，缓冲区还不会反映你自己的添加 `Requery` 。 动态集不使用游标库。

游标库提供了快照 (静态游标) 即使驱动程序通常不支持它们。 如果你的驱动程序已经支持静态游标，则无需加载游标库即可获取快照支持。 如果使用游标库，则只能使用快照和只进记录集。 如果你的驱动程序支持动态 (KEYSET_DRIVEN 游标) ，并且你想要使用它们，则不得使用游标库。 如果要同时使用快照和动态集，则必须将两个不同的对象作为 (两个不同的 `CDatabase` 对象) ，除非你的驱动程序同时支持这两个连接。

## <a name="positioned-updates-and-timestamp-columns"></a><a name="_core_positioned_updates_and_timestamp_columns"></a> 定位更新和时间戳列

> [!NOTE]
> ODBC 数据源可通过 MFC ODBC 类（如本主题中所述）或通过 MFC 数据访问对象 (DAO) 类访问。

> [!NOTE]
> 如果 ODBC 驱动程序支持 `SQLSetPos` （如果可用），则本主题不适用于您的。

大多数第1级驱动程序不支持定位更新。 此类驱动程序依赖于游标库来模拟第2级驱动程序的功能。 游标库通过对不变的字段执行搜索更新来模拟定位的更新支持。

在某些情况下，记录集可能包含时间戳列作为这些不变字段之一。 将 MFC 记录集与包含时间戳列的表结合使用时，会出现两个问题。

第一个问题涉及带有时间戳列的表的可更新快照。 如果您的快照所绑定到的表包含时间戳列，则应在 `Requery` 调用和后 `Edit` 调用 `Update` 。 否则，可能无法再次编辑同一记录。 当你调用， `Edit` 然后 `Update` ，记录将写入数据源并且时间戳列会更新。 如果不调用，则 `Requery` 快照中记录的时间戳值不再与数据源中的相应时间戳匹配。 当您尝试再次更新记录时，由于不匹配，数据源可能会禁止更新。

第二个问题涉及类 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 的限制：与函数一起使用时，与 `RFX_Date` 表之间传输时间和日期信息。 处理 `CTime` 对象会在数据传输过程中以额外的中间处理的形式承担一些开销。 对象的日期范围 `CTime` 也可能对某些应用程序而言过于限制。 函数的新版本 `RFX_Date` 采用 ODBC *TIMESTAMP_STRUCT* 参数而不是 `CTime` 对象。 有关详细信息，请参阅 `RFX_Date` *MFC 参考* 中的 [宏和全局](../../mfc/reference/mfc-macros-and-globals.md)。

## <a name="using-the-cursor-library"></a><a name="_core_using_the_cursor_library"></a> 使用游标库

当你通过调用 [CDatabase：： microsoft.office.interop.visio.documents.open](../../mfc/reference/cdatabase-class.md#openex) 或 [CDatabase：： Open](../../mfc/reference/cdatabase-class.md#open) 连接到数据源时，你可以指定是否将游标库用于数据源。 如果要在该数据源上创建快照，请 `CDatabase::useCursorLib` 在参数中指定选项， `dwOptions` 或将 `OpenEx` *bUseCursorLib* 参数的值指定为 TRUE `Open` (默认值为 true) 。 如果您的 ODBC 驱动程序支持动态集，并且您想要在数据源上打开动态集，请不要使用游标库， (它会屏蔽动态集) 所需的某些驱动程序功能。 在这种情况下，不要在中 `CDatabase::useCursorLib` `OpenEx` 为 *bUseCursorLib* 参数指定 in 或指定 FALSE `Open` 。

## <a name="see-also"></a>请参阅

[ODBC 基础知识](../../data/odbc/odbc-basics.md)
