---
description: 了解有关以下内容的详细信息： TN045：适用于 Long Varchar/Varbinary 的 MFC/数据库支持
title: TN045：对 Long Varchar-Varbinary MFC-Database 支持
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 4e19147ab5ca392307f331b12d3cf24eb5fcc06f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215178"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045：针对长型 Varchar/Varbinary 的 MFC/数据库支持

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

本说明介绍了如何使用 MFC 数据库类检索和发送 ODBC **SQL_LONGVARCHAR** 和 **SQL_LONGVARBINARY** 数据类型。

## <a name="overview-of-long-varcharvarbinary-support"></a>长型 Varchar/Varbinary 支持概述

ODBC **SQL_LONG_VARCHAR** 和 **SQL_LONGBINARY** 数据类型 (在此处称为长数据列，) 可以包含大量数据。 可以通过三种方法来处理此数据：

- 将其绑定到 `CString` / `CByteArray` 。

- 将其绑定到 `CLongBinary` 。

- 不要将其绑定到一起，并手动检索和发送长数据值，而与数据库类无关。

这三种方法都有优点和缺点。

查询的参数的长数据列不受支持。 只支持 outputColumns。

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>将 Long 数据列绑定到 CString/CByteArray

优点：

此方法易于理解，并且你可以使用熟悉的类。 框架为提供 `CFormView` 对 `CString` 的支持 `DDX_Text` 。 你对和类具有很多常规字符串或集合 `CString` 功能 `CByteArray` ，你可以控制在本地分配的用于保存数据值的内存量。 框架在或函数调用期间维护字段数据的旧副本 `Edit` `AddNew` ，框架可以自动检测对数据所做的更改。

> [!NOTE]
> 由于 `CString` 设计用于处理字符数据，并 `CByteArray` 在处理二进制数据时，建议将字符数据 (**SQL_LONGVARCHAR**) `CString` ，并将二进制数据 (**SQL_LONGVARBINARY**) 到中 `CByteArray` 。

和的 RFX 函数 `CString` `CByteArray` 具有一个附加参数，该参数使你可以重写分配的内存的默认大小以保存数据列的检索值。 请注意以下函数声明中的 nMaxLength 参数：

```cpp
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,
    CString& value,
    int nMaxLength = 255,
    int nColumnType =
    SQL_VARCHAR);

void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,
    CByteArray& value,
    int nMaxLength = 255);
```

如果将长数据列检索到 `CString` 或，则 `CByteArray` 返回的最大数据量为，默认值为255字节。 超出此范围的任何内容都将被忽略。 在这种情况下，框架将引发异常 **AFX_SQL_ERROR_DATA_TRUNCATED**。 幸运的是，您可以将 nMaxLength 明确地增加到更大的值，最大值为 **MAXINT**。

> [!NOTE]
> MFC 使用 nMaxLength 的值来设置函数的本地缓冲区 `SQLBindColumn` 。 这是用于存储数据的本地缓冲区，并不会实际影响 ODBC 驱动程序返回的数据量。 `RFX_Text` 和 `RFX_Binary` 仅使用 `SQLFetch` 从后端数据库检索数据的调用。 每个 ODBC 驱动程序对可以在单个提取中返回的数据量有不同的限制。 此限制可能会比 nMaxLength 中设置的值小得多，在这种情况下，将引发异常 **AFX_SQL_ERROR_DATA_TRUNCATED** 。 在这些情况下，切换到使用 `RFX_LongBinary` 而不是 `RFX_Text` 或， `RFX_Binary` 以便可以检索所有数据。

ClassWizard 会将 **SQL_LONGVARCHAR** 绑定到 `CString` ，或将 **SQL_LONGVARBINARY** 绑定到 `CByteArray` 。 如果要分配的字节数超过255，则可以为 nMaxLength 提供一个显式值。

当长数据列绑定到 `CString` 或时 `CByteArray` ，更新字段的工作方式与绑定到 SQL_ **VARCHAR** 或 SQL_ **VARBINARY** 时相同。 在过程中 `Edit` ，当 `Update` 调用来检测对数据值所做的更改并相应地设置列的脏值和 Null 值时，数据值将缓存掉并在之后进行比较。

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>将 Long 数据列绑定到 CLongBinary

如果您的长整型数据列可能包含更多 **MAXINT** 字节的数据，则您可以考虑将其检索到 `CLongBinary` 。

优点：

这将检索整个长数据列，直到达到可用内存。

缺点：

数据保存在内存中。 对于极大量的数据而言，这种方法的成本也很高。 必须 `SetFieldDirty` 为绑定数据成员调用，以确保在操作中包括该字段 `Update` 。

如果在中检索长数据列 `CLongBinary` ，则数据库类将检查 long 数据列的总大小，然后分配一个 `HGLOBAL` 足够大的内存段来保存整个数据值。 然后，数据库类将整个数据值检索到分配的中 `HGLOBAL` 。

如果数据源无法返回 long 数据列的预期大小，则框架将引发异常 **AFX_SQL_ERROR_SQL_NO_TOTAL**。 如果尝试分配 `HGLOBAL` 失败，则会引发标准内存异常。

ClassWizard 会将 **SQL_LONGVARCHAR** 或 **SQL_LONGVARBINARY** 绑定到 `CLongBinary` 。 `CLongBinary`在 "添加成员变量" 对话框中选择作为变量类型。 然后，ClassWizard 将添加 `RFX_LongBinary` 对调用的调用 `DoFieldExchange` ，并递增绑定字段的总数。

若要更新长数据列值，请首先 `HGLOBAL` 通过在的 *m_hData* 成员上调用 **：： GlobalSize** ，确保分配的空间足够大，以便保存新数据 `CLongBinary` 。 如果它太小，请释放 `HGLOBAL` 并分配一个合适的大小。 然后，将 *m_dwDataLength* 设置为反映新的大小。

否则，如果 *m_dwDataLength* 大于你要替换的数据的大小，则可以释放并重新分配 `HGLOBAL` ，或将其保留为已分配。 请确保指定 *m_dwDataLength* 中实际使用的字节数。

## <a name="how-updating-a-clongbinary-works"></a>更新 CLongBinary 的工作原理

不需要了解更新工作的方式 `CLongBinary` ，但它可能会很有用，例如，如果选择此第三种方法，请参阅如何向数据源发送长数据值，如下所述。

> [!NOTE]
> 为了使 `CLongBinary` 字段包含在更新中，必须 `SetFieldDirty` 为字段显式调用。 如果对字段进行了任何更改（包括将其设置为 Null），则必须调用 `SetFieldDirty` 。 还必须调用 `SetFieldNull` ，第二个参数为 **FALSE**，以便将字段标记为具有值。

更新字段时 `CLongBinary` ，数据库类使用 odbc 的 **DATA_AT_EXEC** 机制 (参阅 `SQLSetPos` rgbValue 参数) 上的 odbc 文档。 当框架准备 insert 或 update 语句时，将的 `HGLOBAL` *地址* 设置为列的值，而不是指向包含数据的，并将 `CLongBinary` 长度指示器设置为 **SQL_DATA_AT_EXEC**。  稍后，当 update 语句发送到数据源时， `SQLExecDirect` 将返回 **SQL_NEED_DATA**。 这会提醒框架，此列的参数值实际上是的地址 `CLongBinary` 。 该框架 `SQLGetData` 使用小型缓冲区调用一次，该缓冲区应为驱动程序返回数据的实际长度。 如果驱动程序返回 (BLOB) 的二进制大型对象的实际长度，MFC 会根据需要重新分配足够的空间来提取 BLOB。 如果数据源返回 **SQL_NO_TOTAL**（表示它无法确定 BLOB 的大小），则 MFC 将创建较小的块。 默认初始大小为64K，后续块将是大小的两倍;例如，第二个是128K，第三个是256K，依此类推。 初始大小是可配置的。

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>不绑定：通过 SQLGetData 直接从 ODBC 检索/发送数据

使用此方法，您可以完全绕过数据库类，并亲自处理长数据列。

优点：

如果需要，可以将数据缓存到磁盘，或确定要检索的数据量。

缺点：

您不会获得框架 `Edit` 或 `AddNew` 支持，您必须自行编写代码来执行基本功能 (`Delete` 确实有效，因为它不是列级操作) 。

在这种情况下，长数据列必须位于记录集的选择列表中，但框架不应将其绑定到。 实现此目的的一种方法是，通过或将自己 `GetDefaultSQL` 的 SQL 语句作为 lpszSQL 参数提供给 `CRecordset` 的 `Open` 函数，而不是将额外列与 RFX_ 函数调用进行绑定。 ODBC 要求未绑定字段出现在绑定字段右侧，因此请将未绑定的列添加到选择列表的末尾。

> [!NOTE]
> 由于您的 long 数据列不受框架绑定，因此不会通过调用对其进行更改 `CRecordset::Update` 。 您必须自行创建和发送所需的 SQL **INSERT** 和 **UPDATE** 语句。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
