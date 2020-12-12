---
description: '了解详细信息：记录集：执行联接 (ODBC) '
title: 记录集：执行联接 (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
ms.openlocfilehash: 1c7aa7bfb6925d9f7e916ddb6cd60061667d7859
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204506"
---
# <a name="recordset-performing-a-join-odbc"></a>记录集：执行联接 (ODBC)

本主题适用于 MFC ODBC 类。

## <a name="what-a-join-is"></a>联接是什么

联接操作是一个常见的数据访问任务，可让你使用单个记录集对象处理多个表中的数据。 联接两个或多个表将生成一个记录集，该记录集可包含每个表中的列，但在应用程序中显示为单个表。 有时，联接使用所有表中的所有列，但有时联接中的 SQL **SELECT** 子句只使用每个表中的某些列。 数据库类支持只读联接，但不支持可更新的联接。

若要从联接的表中选择包含列的记录，需要以下项：

- 包含所有要联接的表的名称的表列表。

- 包含所有参与列的名称的列列表。 具有相同名称但来自不同表的列由表名限定。

-  (SQL **WHERE** 子句) 的筛选器，用于指定联接表的列。 此筛选器采用 "KeyCol = Table2. KeyCol" 格式，并实际完成联接。

您可以通过相同的方式联接两个以上的表，方法是将多对列进行相等，每个对都通过 SQL 关键字 **AND** 联接起来。

## <a name="see-also"></a>请参阅

[记录集 (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[记录集：为预定义查询声明类 (ODBC) ](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[记录集：为表声明类 (ODBC) ](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[记录集：重新查询记录集 (ODBC) ](../../data/odbc/recordset-requerying-a-recordset-odbc.md)
