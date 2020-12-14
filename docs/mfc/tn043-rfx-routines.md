---
description: 了解详细信息： TN043： RFX 例程
title: TN043：RFX 例程
ms.date: 06/28/2018
f1_keywords:
- RFX
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
ms.openlocfilehash: 6e5ac8271739e5cab80b79cb915b07e7d25622cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215217"
---
# <a name="tn043-rfx-routines"></a>TN043：RFX 例程

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

此注释描述了记录字段交换 (RFX) 体系结构。 还介绍了如何编写 **RFX_** 过程。

## <a name="overview-of-record-field-exchange"></a>记录字段交换概述

所有记录集字段函数都是用 c + + 代码完成的。 没有特殊的资源或神奇的宏。 机制的核心是必须在每个派生记录集类中重写的虚函数。 它始终按以下形式找到：

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

特殊格式 AFX 注释允许 ClassWizard 查找和编辑此函数中的代码。 与 ClassWizard 不兼容的代码应置于特殊格式注释之外。

在上面的示例中，的 \<recordset_exchange_field_type_call> 格式为：

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

和 \<recordset_exchange_function_call> 的形式如下：

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

大多数 **RFX_** 函数都有三个参数，如上文所示，但有些 (例如 `RFX_Text` ， `RFX_Binary`) 具有其他可选参数。

每个函数中可能包含多个 RFX_ `DoDataExchange` 。

有关随 MFC 一起提供的所有记录集字段交换例程的列表，请参阅 "afxdb"。

记录集字段调用是一种注册内存位置 (通常) 数据成员来存储类的字段数据的方式 `CMySet` 。

## <a name="notes"></a>注释

记录集字段函数旨在仅适用于这些 `CRecordset` 类。 它们通常不能由任何其他 MFC 类使用。

数据的初始值在标准 c + + 构造函数中设置，通常在带有 and 注释的块中 `//{{AFX_FIELD_INIT(CMylSet)` `//}}AFX_FIELD_INIT` 。

每个 **RFX_** 函数都必须支持各种操作，范围从返回字段的已更新状态到存档字段以便为编辑字段做准备。

`DoFieldExchange`为) 实例调用 (的每个函数都会 `SetFieldNull` 在调用时进行自己的 `IsFieldDirty` 初始化 `DoFieldExchange` 。

## <a name="how-does-it-work"></a>工作原理

您无需了解以下各项即可使用记录字段交换。 但是，了解这种情况如何在幕后工作会有助于您编写自己的 exchange 过程。

`DoFieldExchange`成员函数非常类似于 `Serialize` 成员函数，它负责从 ODBC 查询的结果中获取或设置外部窗体 (的数据，) 从/向类中的成员数据。 *PFX* 参数是用于进行数据交换的上下文，与的 *CArchive* 参数类似 `CObject::Serialize` 。 *PFX* (某个 `CFieldExchange` 对象) 具有一个操作指示器，该指示器类似于，但它是 *CArchive* 方向标志的泛化。 RFX 函数可能必须支持下列操作：

- `BindParam` -指示 ODBC 应检索参数数据的位置

- `BindFieldToColumn` -指示 ODBC 必须检索/存放 outputColumn 数据的位置

- `Fixup` -设置 `CString/CByteArray` 长度，设置 NULL 状态位

- `MarkForAddNew` -如果自 AddNew 调用后值已更改，则将其标记为已更新

- `MarkForUpdate` -如果自编辑调用后值已更改，则将其标记为已更新

- `Name` -追加标记为 "已更新" 的字段的字段名称

- `NameValue` - \<column name> 为标记为 "已更新" 的字段追加 "="

- `Value` -追加 "" 后跟分隔符，如 "，" 或 ""

- `SetFieldDirty` -设置状态位脏 (即) 字段已更改

- `SetFieldNull` -设置指示字段的 null 值的状态位

- `IsFieldDirty` -返回脏状态位的值

- `IsFieldNull` -Null 状态位的返回值

- `IsFieldNullable` -如果字段可以包含 NULL 值，则返回 TRUE

- `StoreField` -存档字段值

- `LoadField` -重新加载存档的字段值

- `GetFieldInfoValue` -返回有关字段的常规信息

- `GetFieldInfoOrdinal` -返回有关字段的常规信息

## <a name="user-extensions"></a>用户扩展

可以通过多种方式来扩展默认 RFX 机制。 可以

- 添加新的数据类型。 例如：

    ```cpp
    CBookmark
    ```

- RFX_) 中添加新的 exchange 过程 (。

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- 让 `DoFieldExchange` 成员函数有条件地包含附加 RFX 调用或任何其他有效的 c + + 语句。

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> ClassWizard 不能编辑此类代码，只能在特殊格式注释之外使用。

## <a name="writing-a-custom-rfx"></a>编写自定义 RFX

若要编写自己的自定义 RFX 函数，建议你复制现有 RFX 函数，并将其修改为你自己的目的。 选择要复制的正确 RFX 可以使您的工作更加轻松。 某些 RFX 函数有一些唯一的属性，这些属性在决定要复制哪些属性时应考虑这些属性。

`RFX_Long` 和 `RFX_Int` ：这是最简单的 RFX 函数。 数据值不需要任何特殊解释，并且数据大小是固定的。

`RFX_Single` 与 `RFX_Double` 上面的 RFX_Long 和 RFX_Int 一样，这些函数很简单，可以广泛地利用默认实现。 它们存储在 dbflt 而不是 dbrfx 中，但是，仅当显式引用时才允许加载运行时浮点库。

`RFX_Text` 和 `RFX_Binary` ：这两个函数预分配一个静态缓冲区来保存字符串/二进制信息，并且必须使用 ODBC SQLBindCol 注册这些缓冲区，而不是注册 &值。 因此，这两个函数都有大量的特殊代码。

`RFX_Date`： ODBC 将日期和时间信息单独返回 TIMESTAMP_STRUCT 的数据结构中。 此函数会动态分配一个 TIMESTAMP_STRUCT 作为用于发送和接收日期时间数据的 "代理"。 各种操作都必须在 c + + `CTime` 对象和 TIMESTAMP_STRUCT 代理之间传输日期和时间信息。 这会大大增加此函数的复杂性，但它是一个很好的示例，说明如何使用代理进行数据传输。

`RFX_LongBinary`：这是唯一一个类库 RFX 函数，不使用列绑定来接收和发送数据。 此函数将忽略 BindFieldToColumn 操作，而是在修复操作过程中，分配存储以保存传入的 SQL_LONGVARCHAR 或 SQL_LONGVARBINARY 数据，然后执行 SQLGetData 调用以将值检索到分配的存储中。 准备将数据值发送回数据源时 (如名称值和值运算) ，此函数使用 ODBC 的 DATA_AT_EXEC 功能。 有关使用 SQL_LONGVARBINARY 和 SQL_LONGVARCHARs 的详细信息，请参阅 [技术说明 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) 。

编写您自己的 **RFX_** 函数时，通常可以使用 `CFieldExchange::Default` 来实现给定的操作。 查看相关操作的默认实现。 如果执行要在 **RFX_** 函数中编写的操作，则可以将委托给 `CFieldExchange::Default` 。 可以在 dbrfx 中查看调用的示例 `CFieldExchange::Default`

务必 `IsFieldType` 在 RFX 函数的开头调用，并在返回 FALSE 时立即返回。 此机制使参数操作不会在 *outputColumns* 上执行，反之亦然 (例如 `BindParam` 在 *outputColumn*) 上调用。 此外， `IsFieldType` 会自动跟踪 *outputColumns* (*m_nFields*) 和参数 (*m_nParams*) 的计数。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
