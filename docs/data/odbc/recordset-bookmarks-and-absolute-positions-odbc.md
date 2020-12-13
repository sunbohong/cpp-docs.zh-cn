---
description: '了解详细信息：记录集：书签和绝对位置 (ODBC) '
title: 记录集：书签和绝对位置 (ODBC)
ms.date: 11/04/2016
f1_keywords:
- SetAbsolutePosition
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
ms.openlocfilehash: b52ca2e43a89a6cab0e9197d8dbf32c321feca5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186111"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>记录集：书签和绝对位置 (ODBC)

本主题适用于 MFC ODBC 类。

在记录集中导航时，通常需要一种方法来返回特定记录。 记录的书签和绝对位置提供了两种此类方法。

本主题介绍：

- [如何使用书签](#_core_bookmarks_in_mfc_odbc)。

- [如何使用绝对位置设置当前记录](#_core_absolute_positions_in_mfc_odbc)。

## <a name="bookmarks-in-mfc-odbc"></a><a name="_core_bookmarks_in_mfc_odbc"></a> MFC ODBC 中的书签

书签唯一标识一条记录。 当您在记录集中导航时，您不能始终依赖记录的绝对位置，因为可以从记录集中删除记录。 跟踪记录位置的可靠方法是使用其书签。 类 `CRecordset` 为提供成员函数：

- 获取当前记录的书签，以便可以将其保存到 ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)) 的变量中。

- 通过指定其书签（你之前保存在变量 ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)) 中），快速移动到给定记录。

下面的示例演示如何使用这些成员函数标记当前记录并稍后返回到该记录：

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

不需要从 [CDBVariant 类](../../mfc/reference/cdbvariant-class.md) 对象中提取基础数据类型。 将值分配给， `GetBookmark` 并返回到该书签 `SetBookmark` 。

> [!NOTE]
> 根据 ODBC 驱动程序和记录集类型，书签可能不受支持。 可以通过调用 [CRecordset：： CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark)轻松确定是否支持书签。 而且，如果支持书签，则必须通过在 `CRecordset::useBookmarks` [CRecordset：： Open](../../mfc/reference/crecordset-class.md#open) 成员函数中指定选项来显式选择实现它们。 还应检查某些记录集操作后书签的持久性。 例如，如果 `Requery` 记录集，书签可能不再有效。 调用 [CDatabase：： GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 以检查是否可以安全调用 `SetBookmark` 。

## <a name="absolute-positions-in-mfc-odbc"></a><a name="_core_absolute_positions_in_mfc_odbc"></a> MFC ODBC 中的绝对位置

除书签外，类 `CRecordset` 还允许您通过指定序号位置设置当前记录。 这称为绝对定位。

> [!NOTE]
> 绝对定位在只进记录集上不可用。 有关只进记录集的详细信息，请参阅 [Recordset (ODBC) ](../../data/odbc/recordset-odbc.md)。

若要使用绝对位置移动当前记录指针，请调用 [CRecordset：： SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition)。 向传递值时，与 `SetAbsolutePosition` 序号位置相对应的记录将成为当前记录。

> [!NOTE]
> 记录的绝对位置可能不可靠。 如果用户从记录集中删除记录，则所有后续记录的序号位置都将更改。 建议使用书签来移动当前记录。 有关详细信息，请参阅 [MFC ODBC 中的书签](#_core_bookmarks_in_mfc_odbc)。

有关记录集导航的详细信息，请参阅 [记录集： (ODBC) 滚动 ](../../data/odbc/recordset-scrolling-odbc.md)。

## <a name="see-also"></a>请参阅

[记录集 (ODBC)](../../data/odbc/recordset-odbc.md)
