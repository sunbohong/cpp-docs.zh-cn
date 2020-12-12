---
description: '了解详细信息： SQL：自定义记录集的 SQL 语句 (ODBC) '
title: SQL：自定义记录集的 SQL 语句 (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: 73765ed66dacbc017cca6236ae5a90388390fa45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278683"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL：自定义记录集的 SQL 语句 (ODBC)

本主题介绍：

- 框架如何构造 SQL 语句

- 如何替代 SQL 语句

> [!NOTE]
> 此信息适用于 MFC ODBC 类。 如果使用的是 MFC DAO 类，请参阅 DAO 帮助中的 "Microsoft Jet 数据库引擎 SQL 和 ANSI SQL 比较" 主题。

## <a name="sql-statement-construction"></a>SQL 语句构造

记录集基本记录对 SQL **SELECT** 语句的选择。 使用向导声明类时，它会 `GetDefaultSQL` 为名为) 的记录集类编写如下所 (示的成员函数的重写版本 `CAuthors` 。

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

默认情况下，此重写将返回您在向导中指定的表名。 在此示例中，表名为 "AUTHORS"。 以后调用记录集的 `Open` 成员函数时，将 `Open` 构造如下格式的最终 **SELECT** 语句：

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

在 `table-name` 中，通过调用获取 `GetDefaultSQL` ， `rfx-field-list` 它是从中 RFX 函数调用获取的 `DoFieldExchange` 。 这就是您为 **SELECT** 语句所获得的内容，除非您还可以使用参数或筛选器来修改默认语句。

> [!NOTE]
> 如果指定的列名包含 (或可能包含) 空间，则必须用方括号将该名称括起来。 例如，名称 "First Name" 应为 "[First Name]"。

若要重写默认的 **select** 语句，请在调用时传递包含完整 **SELECT** 语句的字符串 `Open` 。 记录集使用您提供的字符串，而不是构建其自己的默认字符串。 如果替换语句包含 **WHERE** 子句，请不要在中指定筛选器， `m_strFilter` 因为这样就会有两个筛选语句。 同样，如果替换语句包含 **ORDER BY** 子句，则不要在中指定排序方式， `m_strSort` 这样就不会有两个 sort 语句了。

> [!NOTE]
> 如果在筛选器中使用文字字符串 (或 SQL 语句的其他部分) ，则可能必须使用以 DBMS 特定的文本前缀和文本后缀字符 (或) 字符括起来， (用指定的) 分隔符将此类字符串括起来。

对于外部联接等操作，你可能还会遇到特殊语法要求，具体取决于你的 DBMS。 使用 ODBC 函数从 DBMS 的驱动程序中获取此信息。 例如，调用 `::SQLGetTypeInfo` 特定数据类型（例如 `SQL_VARCHAR` ）来请求 LITERAL_PREFIX 和 LITERAL_SUFFIX 字符。 如果要编写与数据库无关的代码，请参阅[ODBC 程序员参考](/sql/odbc/reference/odbc-programmer-s-reference)中的[附录 C： SQL 语法](/sql/odbc/reference/appendixes/appendix-c-sql-grammar)，了解详细的语法信息。

Recordset 对象将构造用于选择记录的 SQL 语句，除非传递自定义 SQL 语句。 完成此操作的方式主要取决于在成员函数的 *lpszSQL* 参数中传递的值 `Open` 。

SQL **SELECT** 语句的一般形式为：

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

将 **DISTINCT** 关键字添加到记录集的 SQL 语句的一种方法是将关键字嵌入到中的第一个 RFX 函数调用中 `DoFieldExchange` 。 例如：

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> 仅将此方法用于以只读方式打开的记录集。

## <a name="overriding-the-sql-statement"></a>重写 SQL 语句

下表显示了 *lpszSQL* 参数的可能的 `Open` 。 表中的事例如下所述。

**LpszSQL 参数和生成的 SQL 字符串**

|案例|在 lpszSQL 中传递的内容|生成的 SELECT 语句|
|----------|------------------------------|------------------------------------|
|1|Null|**从***表名称***选择** *rfx-列表*<br /><br /> `CRecordset::Open` 调用 `GetDefaultSQL` 以获取表名称。 生成的字符串是事例2到步骤5中的一种，具体取决于返回的内容 `GetDefaultSQL` 。|
|2|表名|**从***表名称***选择** *rfx-列表*<br /><br /> 字段列表是从中 RFX 语句获取的 `DoFieldExchange` 。 如果 `m_strFilter` 和不 `m_strSort` 为空，则添加 **WHERE** 和/或 **ORDER BY** 子句。|
|三维空间 \*|完整的 **SELECT** 语句，但不包含 **WHERE** 或 **ORDER by** 子句|作为传递。 如果 `m_strFilter` 和不 `m_strSort` 为空，则添加 **WHERE** 和/或 **ORDER BY** 子句。|
|4 \*|包含 **WHERE** 和/或 **ORDER by** 子句的完整 **SELECT** 语句|作为传递。 `m_strFilter` 和/或 `m_strSort` 必须保持为空，或者生成了两个筛选器和/或排序语句。|
|5 \*|调用存储过程|作为传递。|

\*`m_nFields`必须小于或等于 **SELECT** 语句中指定的列数。 **SELECT** 语句中指定的每一列的数据类型必须与相应 RFX 输出列的数据类型相同。

### <a name="case-1---lpszsql--null"></a>Case 1 lpszSQL = NULL

记录集选择取决于 `GetDefaultSQL` 调用它时返回的内容 `CRecordset::Open` 。 案例2到步骤5描述了可能的字符串。

### <a name="case-2---lpszsql--a-table-name"></a>Case 2 lpszSQL = 表名

记录集使用记录字段交换 (RFX) 从记录集类的重写中 RFX 函数调用中提供的列名生成列列表 `DoFieldExchange` 。 如果你使用向导来声明记录集类，则此示例的结果与 case 1 (相同，前提是你传递的是你在向导) 中指定的相同的表名。 如果不使用向导来编写类，请使用 case 2 作为构造 SQL 语句的最简单方法。

下面的示例构造了从 MFC 数据库应用程序选择记录的 SQL 语句。 当框架调用 `GetDefaultSQL` 成员函数时，函数将返回表的名称 `SECTION` 。

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

若要获取 SQL **SELECT** 语句的列的名称，框架将调用 `DoFieldExchange` 成员函数。

```cpp
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Text(pFX, "CourseID", m_strCourseID);
    RFX_Text(pFX, "InstructorID", m_strInstructorID);
    RFX_Text(pFX, "RoomNo", m_strRoomNo);
    RFX_Text(pFX, "Schedule", m_strSchedule);
    RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

完成后，SQL 语句如下所示：

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Case 3 lpszSQL = SELECT/FROM 语句

您可以手动指定列列表，而不是依赖 RFX 自动构造列列表。 在以下情况下，你可能希望执行此操作：

- 需要在 **SELECT** 后指定 **DISTINCT** 关键字。

   列列表应与列名称和类型匹配的顺序与其在中列出的顺序相同 `DoFieldExchange` 。

- 您有理由使用 ODBC 函数手动检索列值， `::SQLGetData` 而不是依赖 RFX 来绑定和检索列。

   例如，你可能想要在分发应用程序后，容纳应用程序的客户添加到数据库表中的新列。 你需要添加这些额外的字段数据成员，这些字段在你使用向导声明类时未知。

   列列表应与列名称和类型匹配的顺序与其在中列出的顺序相同 `DoFieldExchange` ，后跟手动绑定的列的名称。 有关详细信息，请参阅 [记录集：动态绑定数据列 (ODBC) ](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)。

- 您希望通过在 **from** 子句中指定多个表来联接表。

   有关信息和示例，请参阅 [记录集：执行联接 (ODBC) ](../../data/odbc/recordset-performing-a-join-odbc.md)。

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>情况 4 lpszSQL = SELECT/FROM + WHERE and/or ORDER BY

您可以指定所有内容：基于) 中 RFX 调用 (列列表 `DoFieldExchange` 、表列表以及 **WHERE** 和/或 **ORDER by** 子句的内容。 如果以这种方式指定 **WHERE** 和/或 **ORDER BY** 子句，请不要使用 `m_strFilter` 和/或 `m_strSort` 。

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Case 5 lpszSQL = 存储过程调用

如果需要调用预定义查询 (例如 Microsoft SQL Server 数据库中的存储过程) ，则必须在传递给 *lpszSQL* 的字符串中写入 **call** 语句。 向导不支持声明记录集类来调用预定义查询。 并非所有预定义的查询都返回记录。

如果预定义查询不返回记录，则可以 `CDatabase` 直接使用成员函数 `ExecuteSQL` 。 对于返回记录的预定义查询，还必须 `DoFieldExchange` 为该过程返回的任何列手动写入 RFX 调用。 RFX 调用的顺序必须与预定义查询的顺序相同并返回相同的类型。 有关详细信息，请参阅 [记录集：为预定义查询声明类 (ODBC) ](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)。

## <a name="see-also"></a>请参阅

[SQL： SQL 和 c + + 数据类型 (ODBC) ](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL：在 ODBC)  (进行直接 SQL 调用 ](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
