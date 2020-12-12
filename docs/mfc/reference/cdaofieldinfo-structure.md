---
description: 了解详细信息： CDaoFieldInfo 结构
title: CDaoFieldInfo 结构
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: 8cb297e767fed023ff7b6c2fe7efe5dd41a1621a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250863"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 结构

该 `CDaoFieldInfo` 结构包含有关为 (DAO) 的数据访问对象定义的字段对象的信息。

DAO 受 Office 2013 的支持。 DAO 3.6 是最终版本，被视为已过时。

## <a name="syntax"></a>语法

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
对 field 对象进行唯一命名。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。

*m_nType*<br/>
指示字段的数据类型的值。 有关详细信息，请参阅 DAO 帮助中的 "类型属性" 主题。 此属性的值可以是下列值之一：

- `dbBoolean` 是/否，与 TRUE/FALSE 相同

- `dbByte` 位

- `dbInteger` 短暂

- `dbLong` 漫长

- `dbCurrency` 货币请参阅 MFC 类 [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` 单个

- `dbDouble` 仔细

- `dbDate` 日期/时间;请参阅 MFC 类 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` 全文请参阅 MFC 类 [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` 长整型 (OLE 对象) ;你可能希望使用 MFC 类 [CByteArray](../../mfc/reference/cbytearray-class.md) ，而不是类， `CLongBinary` 因为更 `CByteArray` 丰富且更易于使用。

- `dbMemo` "请参见 MFC 类 `CString`

- `dbGUID` 用于远程过程调用的全局唯一标识符/全局唯一标识符。 有关详细信息，请参阅 DAO 帮助中的 "类型属性" 主题。

> [!NOTE]
> 不要将字符串数据类型用于二进制数据。 这会导致你的数据通过 Unicode/ANSI 转换层，导致增加开销，并可能导致意外的转换。

*m_lSize*<br/>
一个值，该值指示 DAO 字段对象的最大大小（以字节为单位），该对象包含文本或数字值的字段对象的固定大小。 有关详细信息，请参阅 DAO 帮助中的主题 "Size 属性"。 大小可以为下列值之一：

|类型|大小(字节)|描述|
|----------|--------------------|-----------------|
|`dbBoolean`|1 个字节|是/否 (与 True/False 相同) |
|`dbByte`|1|Byte|
|`dbInteger`|2|Integer|
|`dbLong`|4|Long|
|`dbCurrency`|8|货币 ([COleCurrency](../../mfc/reference/colecurrency-class.md)) |
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|日期/时间 ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)) |
|`dbText`|1 - 255| ([CString](../../atl-mfc-shared/reference/cstringt-class.md)) 文本|
|`dbLongBinary`|0|Long Binary (OLE 对象; [CByteArray](../../mfc/reference/cbytearray-class.md);使用而不是 `CLongBinary`) |
|`dbMemo`|0|备注型 ([CString](../../atl-mfc-shared/reference/cstringt-class.md)) |
|`dbGUID`|16|用于远程过程调用的全局唯一标识符/全局唯一标识符。|

*m_lAttributes*<br/>
指定 tabledef、recordset、querydef 或 index 对象所包含的 field 对象的特征。 返回的值可以是这些常量的总和，使用 c + + 按位 "或" (**&#124;**) 运算符来创建：

- `dbFixedField` 字段大小固定 (数值字段) 的默认值。

- `dbVariableField` 字段大小 (仅) 文本字段。

- `dbAutoIncrField` 新记录的字段值会自动递增为一个唯一的长整数，该整数不能更改。 仅支持 Microsoft Jet 数据库表。

- `dbUpdatableField` 可以更改该字段的值。

- `dbDescending` 字段按降序排序 (Z A 或 100-0) 顺序 (仅适用于索引对象的字段集合中的字段对象;在 MFC 中，索引对象本身包含在) 的 tabledef 对象中。 如果省略此常量，则字段将按升序 (a-z 或 0-100) 顺序 (默认) 。

检查此属性的设置时，可以使用 c + + 按位 AND 运算符 (**&**) 来测试特定属性。 设置多个属性时，可以将相应的常量与按位 "或" (**&#124;**) "运算符组合在一起。 有关详细信息，请参阅 DAO 帮助中的 "属性属性" 主题。

*m_nOrdinalPosition*<br/>
一个值，该值指定要使 DAO 字段对象表示的字段相对于其他字段的显示数值顺序。 可以用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)设置此属性。 有关详细信息，请参阅 DAO 帮助中的主题 "OrdinalPosition 属性"。

*m_bRequired*<br/>
指示 DAO 字段对象是否需要非 Null 值。 如果此属性为 TRUE，则字段不允许为 Null 值。 如果 "必需" 设置为 "FALSE"，则字段可以包含空值，还可以包含满足 "允许空值" 和 "有效性规则" 属性设置指定的条件的值。 有关详细信息，请参阅 DAO 帮助中的主题 "Required 属性"。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

*m_bAllowZeroLength*<br/>
指示空字符串 ( "" ) 是否为具有 Text 或备注数据类型的 DAO 字段对象的有效值。 如果此属性为 TRUE，则空字符串是有效值。 可以将此属性设置为 FALSE，以确保不能使用空字符串设置字段的值。 有关详细信息，请参阅 DAO 帮助中的主题 "可为空属性"。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

*m_lCollatingOrder*<br/>
指定文本中用于字符串比较或排序的排序顺序的序列。 有关详细信息，请参阅 DAO 帮助中的 "自定义用于数据访问的 Windows 注册表设置" 主题。 有关返回的可能值的列表，请参阅 `m_lCollatingOrder` [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 结构的成员。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

*m_strForeignName*<br/>
一个值，该值在关系中指定外表中的 DAO 字段对象的名称，该表与主表中的字段相对应。 有关详细信息，请参阅 DAO 帮助中的主题 "ForeignName 属性"。

*m_strSourceField*<br/>
指示作为 tabledef、recordset 或 querydef 对象所包含的 DAO 字段对象的数据的原始源的字段名称。 此属性指示与字段对象关联的原始字段名称。 例如，您可以使用此属性来确定其名称与基础表中的字段名称不相关的查询字段中的数据的原始源。 有关详细信息，请参阅 DAO 帮助中的主题 "SourceField，SourceTable Properties"。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

*m_strSourceTable*<br/>
指示作为 tabledef、recordset 或 querydef 对象所包含的 DAO 字段对象的数据的原始源的表的名称。 此属性指示与 field 对象关联的原始表名称。 例如，您可以使用此属性来确定其名称与基础表中的字段名称不相关的查询字段中的数据的原始源。 有关详细信息，请参阅 DAO 帮助中的主题 "SourceField，SourceTable Properties"。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

*m_strValidationRule*<br/>
一个值，该值在字段更改或添加到表中时对其数据进行验证。 有关详细信息，请参阅 DAO 帮助中的主题 "有效性规则属性"。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

有关 tabledefs 的相关信息，请参阅 `m_strValidationRule` [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 结构的成员。

*m_strValidationText*<br/>
一个值，该值指定当 DAO 字段对象的值不满足 ValidationRule 属性设置指定的验证规则时，应用程序显示的消息文本。 有关详细信息，请参阅 DAO 帮助中的主题 "有效性文本属性"。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

*m_strDefaultValue*<br/>
DAO 字段对象的默认值。 创建新记录时，"默认值" 属性设置会自动输入为字段的值。 有关详细信息，请参阅 DAO 帮助中的主题 "DefaultValue 属性"。 可以使用 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)为 tabledef 设置此属性。

## <a name="remarks"></a>备注

对主要、次要和以上的引用指示 `GetFieldInfo` 类 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)和 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)类中的成员函数返回信息的方式。

字段对象不由 MFC 类表示。 相反，以下类的 DAO 对象是以下类的基础 MFC 对象： [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)和 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)。 这些类提供成员函数来访问某些字段信息项，或者可以 `CDaoFieldInfo` 通过调用 `GetFieldInfo` 包含对象的成员函数，一次通过对象访问所有这些项。

除了使用来检查对象属性之外，还可以使用 `CDaoFieldInfo` 构造用于在 tabledef 中创建新字段的输入参数。 更简单的选项可用于此任务，但如果你想要更精细地控制，则可以使用采用参数的 [CDaoTableDef：： CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) 版本 `CDaoFieldInfo` 。

由成员函数检索的信息 `GetFieldInfo` (包含字段) 的类存储在 `CDaoFieldInfo` 结构中。 调用 `GetFieldInfo` 其字段集合中存储字段对象的包含对象的成员函数。 `CDaoFieldInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoFieldInfo` 。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef：： Issomapper.getfieldinfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset：： Issomapper.getfieldinfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef：： Issomapper.getfieldinfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
