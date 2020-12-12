---
description: '了解详细信息：记录集：对记录进行排序 (ODBC) '
title: 记录集：对记录进行排序 (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: fbf2ef3c42061bac9b41550a0c44a20f68c099b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204415"
---
# <a name="recordset-sorting-records-odbc"></a>记录集：对记录进行排序 (ODBC)

本主题适用于 MFC ODBC 类。

本主题介绍如何对记录集进行排序。 您可以指定一个或多个作为排序依据的列，并且可以指定升序或降序 (**ASC** 或 **DESC**; **ASC** 是每个指定列的默认) 。 例如，如果指定两个列，则先对第一个名为的列，然后在名为的第二列上排序记录。 SQL **ORDER by** 子句定义了排序。 当框架将 **ORDER BY** 子句追加到记录集的 SQL 查询中时，子句会控制选择的排序。

你必须在构造对象之后、调用其成员函数之前建立记录集的排序顺序 `Open` (或者在调用之前 `Requery` `Open` 已) 调用成员函数的现有记录集对象的成员函数之前建立记录集的排序顺序。

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>指定记录集对象的排序顺序

1. 构造一个新的记录集对象 (或准备) 现有的记录集对象 `Requery` 。

1. 设置对象的 [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) 数据成员的值。

   排序方式为以 null 值结束的字符串。 它包含 **ORDER by** 子句的内容，但不包含关键字 **order by**。 例如，使用：

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. 设置所需的任何其他选项，例如筛选器、锁定模式或参数。

1. `Open`为新对象 (或 `Requery`) 的现有对象调用。

所选记录按指定顺序排序。 例如，若要按姓氏的降序顺序对一组学生记录进行排序，然后按名字进行排序，请执行以下操作：

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

记录集包含所有学生记录，按降序排序 (Z 到) 按姓排序，再按名字排序。

> [!NOTE]
> 如果你选择通过将自己的 SQL 字符串传递到来替代记录集的默认 SQL 字符串 `Open` ，则如果你的自定义字符串具有 **ORDER by** 子句，则不要设置排序。

## <a name="see-also"></a>请参阅

[记录集 (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[记录集：参数化记录集 (ODBC) ](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[记录集：筛选记录 (ODBC) ](../../data/odbc/recordset-filtering-records-odbc.md)
