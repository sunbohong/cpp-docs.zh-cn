---
description: 了解详细信息：数据源：以编程方式在 ODBC 数据源中创建表
title: 以编程方式在 ODBC 数据源中创建表
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: b195cc4fb81f1caed0b280c5df6a2032f4944ddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155704"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>数据源：以编程方式在 ODBC 数据源中创建表

本主题说明如何使用类的成员函数为数据源创建表 `ExecuteSQL` `CDatabase` ，并向函数传递包含 **CREATE TABLE** SQL 语句的字符串。

有关 MFC 中 ODBC 数据源的一般信息，请参阅 [Data Source (ODBC) ](../../data/odbc/data-source-odbc.md)。 主题 [数据源：以编程方式配置 ODBC 数据源](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) 介绍了如何创建数据源。

建立数据源后，可以使用 `ExecuteSQL` 成员函数和 **CREATE TABLE** SQL 语句轻松地创建表。 例如，如果你有一个名为的 `CDatabase` 对象 `myDB` ，则可以使用以下 MFC 代码创建一个表：

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

此代码示例在由维护的 Microsoft Access 数据源连接中创建一个名为 "办事处" 的表 `myDB` ; 该表包含两个字段： "OfficeID" 和 "OfficeName"。

> [!NOTE]
> **CREATE TABLE** SQL 语句中指定的字段类型可能会因所使用的 ODBC 驱动程序而异。 Microsoft Query 计划 (与 Visual C++ 1.5) 分布式是一种了解哪些字段类型可用于数据源的方法。 在 Microsoft 查询中，单击 " **文件**"，单击 " **Table_Definition**"，从数据源中选择一个表，然后查看 " **类型** " 组合框中显示的类型。 还存在用于创建索引的 SQL 语法。

## <a name="see-also"></a>请参阅

[ODBC) 的数据源 (](../../data/odbc/data-source-odbc.md)
