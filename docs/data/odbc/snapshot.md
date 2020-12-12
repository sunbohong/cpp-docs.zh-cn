---
description: 了解详细信息：快照
title: 快照
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
ms.openlocfilehash: 33505eb02613f672d09b889a09382ce3b8cf19cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204285"
---
# <a name="snapshot"></a>快照

快照是反映数据在创建快照时存在的静态视图的记录集。 打开快照并移动到所有记录后，在通过调用重新生成快照之前，它包含的记录集及其值不会更改 `Requery` 。

> [!NOTE]
> 本主题适用于 MFC ODBC 类。 如果使用的是 MFC DAO 类而不是 MFC ODBC 类，请参阅 [CDaoRecordset：： Open](../../mfc/reference/cdaorecordset-class.md#open) 了解快照类型记录集的说明。

您可以创建具有数据库类的可更新或只读快照。 与动态集不同，可更新的快照不会反映其他用户对记录的值所做的更改，但会反映程序所做的更新和删除。 在调用之前，添加到快照的记录将不会对快照可见 `Requery` 。

> [!TIP]
> 快照是一个 ODBC 静态游标。 静态游标在滚动到该记录之前，实际上不会获得一行数据。 若要确保立即检索所有记录，可以滚动到记录集的末尾，然后滚动到要查看的第一条记录。 但请注意，滚动到末尾需要额外的开销，从而降低性能。

当您在操作过程中需要数据保持固定时，快照是最有价值的，就像生成报表或执行计算时。 尽管如此，数据源也可能与快照之间相差很大，因此你可能想要随时重建。

快照支持基于 ODBC 游标库，此库提供静态游标和定位更新 (任何一级驱动程序的可更新性) 所需的更新。 若要进行此支持，必须在内存中加载游标库 DLL。 构造 `CDatabase` 对象并调用其 `OpenEx` 成员函数时，必须指定 `CDatabase::useCursorLib` *dwOptions* 参数的选项。 如果调用 `Open` 成员函数，则默认情况下会加载游标库。 如果使用的是动态集而不是快照，则不希望加载游标库。

仅当构造对象时加载 ODBC 游标库， `CDatabase` 或使用的 odbc 驱动程序支持静态游标时，快照才可用。

> [!NOTE]
> 对于某些 ODBC 驱动程序，) 可能无法更新静态游标 (快照。 查看驱动程序文档以了解支持的游标类型和它们支持的并发类型。 若要确保可更新的快照，请确保在创建对象时将游标库加载到内存中 `CDatabase` 。 有关详细信息，请参阅 [odbc： Odbc 游标库](../../data/odbc/odbc-the-odbc-cursor-library.md)。

> [!NOTE]
> 如果要同时使用快照和动态集，则必须在两个不同的 `CDatabase` 对象)  (两个不同的连接。

有关快照与所有记录集共享的属性的详细信息，请参阅 [Recordset (ODBC) ](../../data/odbc/recordset-odbc.md)。 有关 ODBC 和快照的详细信息，包括 ODBC 游标库，请参阅 [odbc](../../data/odbc/odbc-basics.md)。

## <a name="see-also"></a>请参阅

[ODBC)  (打开数据库连接 ](../../data/odbc/open-database-connectivity-odbc.md)
