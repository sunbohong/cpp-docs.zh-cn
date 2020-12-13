---
description: '了解详细信息：记录集：批量添加记录 (ODBC) '
title: 记录集：批量添加记录 (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: 5cb47fc8e96a38b2e5cc6c83cf464f28f2a85aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340393"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>记录集：批量添加记录 (ODBC)

本主题适用于 MFC ODBC 类。

MFC [CRecordset](../../mfc/reference/crecordset-class.md) 类提供了一种新的优化，可在将新记录批量添加到表时提高效率。

> [!NOTE]
> 本主题适用于从 `CRecordset` 派生的对象，其中尚未实现批量提取行。 如果使用批量取行，请参阅 [记录集：批量提取记录 (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)。

对于 [CRecordset：： Open](../../mfc/reference/crecordset-class.md#open)成员函数的 *dwOptions* 参数，可以使用新的选项， `optimizeBulkAdd` 在不调用或的情况下连续添加多条记录，从而提高性能 `Requery` `Close` 。 只有那些在第一次调用之前已更新的字段 `Update` 将被标记为 "已更新" 以进行后续 `AddNew` / `Update` 调用。

如果使用数据库类来利用 `::SQLSetPos` ODBC API 函数来添加、编辑和删除记录，则不需要进行此优化。

如果已加载 ODBC 游标库，或者 ODBC 驱动程序不支持通过添加、编辑和删除，则 `::SQLSetPos` 这一优化应该会提高大容量添加性能。 若要启用此优化，请在记录集的调用中将 *dwOptions* 参数设置 `Open` 为以下内容：

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>请参阅

[记录集 (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[记录集： (ODBC) 添加、更新和删除记录 ](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[记录集： (ODBC) 锁定记录 ](../../data/odbc/recordset-locking-records-odbc.md)
