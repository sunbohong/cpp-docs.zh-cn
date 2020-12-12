---
description: 了解详细信息： CMFCFontInfo 类
title: CMFCFontInfo 类
ms.date: 11/04/2016
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
ms.openlocfilehash: 0922e07f268509cd4b5552a6123d8d3465a426bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265410"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo 类

`CMFCFontInfo`类描述字体的名称和其他属性。

## <a name="syntax"></a>语法

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCFontInfo`|构造 `CMFCFontInfo` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCFontInfo::GetFullName](#getfullname)|检索字体的连接名称及其字符集 (脚本) 。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCFontInfo：： m_nCharSet](#m_ncharset)|一个值，该值指定与字体关联 (脚本) 的字符集。|
|[CMFCFontInfo：： m_nPitchAndFamily](#m_npitchandfamily)|一个值，该值指定字体的间距和系列。|
|[CMFCFontInfo：： m_nType](#m_ntype)|一个指定字体类型的值。|
|[CMFCFontInfo：： m_strName](#m_strname)|字体的名称;例如， **Arial**。|
|[CMFCFontInfo：： m_strScript](#m_strscript)|与字体关联 (脚本) 的字符集名称。|

## <a name="remarks"></a>备注

可以将对象附加 `CMFCFontInfo` 到 [CMFCToolBarFontComboBox 类](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 类的项。 调用 [CMFCToolBarFontComboBox：： GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) 方法来检索指向对象的指针 `CMFCFontInfo` 。

## <a name="example"></a>示例

下面的示例演示如何使用类的各种成员 `CMFCFontInfo` 。 该示例演示如何 `CMFCFontInfo` 从获取对象 `CMFCRibbonFontComboBox` ，以及如何访问它的局部变量。 此示例是 [MSOffice 2007 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>要求

**标头：** afxtoolbarfontcombobox

## <a name="cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a> CMFCFontInfo::CMFCFontInfo

构造 `CMFCFontInfo` 对象。

```
CMFCFontInfo(
    LPCTSTR lpszName,
    LPCTSTR lpszScript,
    BYTE nCharSet,
    BYTE nPitchAndFamily,
    int nType);

CMFCFontInfo(const CMFCFontInfo& src);
```

### <a name="parameters"></a>parameters

*lpszName*<br/>
中字体的名称。 有关详细信息，请参阅 `lfFaceName` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 结构的成员。

*lpszScript*<br/>
中脚本的名称 (字体的字符集) 。

*nCharSet*<br/>
中一个值，该值指定字体 (脚本) 的字符集。 有关详细信息，请参阅 `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 结构的成员。

*nPitchAndFamily*<br/>
中一个值，该值指定字体的间距和系列。 有关详细信息，请参阅 `lfPitchAndFamily` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 结构的成员。

nType<br/>
中一个指定字体类型的值。 此参数可以是 DEVICE_FONTTYPE、RASTER_FONTTYPE 和 TRUETYPE_FONTTYPE 的按位组合 (或) 。

*src*<br/>
中一个现有的 `CMFCFontInfo` 对象，其成员用于构造此 `CMFCFontInfo` 对象。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

本文档使用术语 " *字符集* " 和 " *脚本* "。 *脚本*（也称为写入系统）是用于以一种或多种语言编写这些字符的字符和规则的集合。 字符集合包含该脚本中使用的字母和标点。 例如，拉丁语脚本用于在美国中口述的英语，其中的字母表包含从 A 到 Z 的字符。 `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 结构的成员指定了字符集。 例如，值 ANSI_CHARSET 指定 ANSI 字符集，其中包括拉丁脚本的字母表。

## <a name="cmfcfontinfogetfullname"></a><a name="getfullname"></a> CMFCFontInfo::GetFullName

检索字体的连接名称及其字符集 (脚本) 。

```
CString GetFullName() const;
```

### <a name="return-value"></a>返回值

一个字符串，其中包含字体名称和脚本。

### <a name="remarks"></a>备注

使用此方法可获取字体的完整名称。 例如，如果字体名称为 **Arial** ，字体脚本为 **西里尔语**，则此方法返回 "Arial (西里尔文) "。

## <a name="cmfcfontinfom_ncharset"></a><a name="m_ncharset"></a> CMFCFontInfo：： m_nCharSet

一个值，该值指定与字体关联 (脚本) 的字符集。

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>备注

有关详细信息，请参阅 [CMFCFontInfo：： CMFCFontInfo](#cmfcfontinfo)构造函数的 *nCharSet* 参数。

## <a name="cmfcfontinfom_npitchandfamily"></a><a name="m_npitchandfamily"></a> CMFCFontInfo：： m_nPitchAndFamily

一个值，该值指定字体的 (点大小) 和系列 (例如，serif、sans-serif 和等宽) 。

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>备注

有关详细信息，请参阅 [CMFCFontInfo：： CMFCFontInfo](#cmfcfontinfo)构造函数的 *nPitchAndFamily* 参数。

## <a name="cmfcfontinfom_ntype"></a><a name="m_ntype"></a> CMFCFontInfo：： m_nType

一个指定字体类型的值。

```
const int m_nType;
```

### <a name="remarks"></a>备注

有关详细信息，请参阅 [CMFCFontInfo：： CMFCFontInfo](#cmfcfontinfo)构造函数的 *n* 参数。

## <a name="cmfcfontinfom_strname"></a><a name="m_strname"></a> CMFCFontInfo：： m_strName

字体的名称：例如， **Arial**。

```
const CString m_strName;
```

### <a name="remarks"></a>备注

有关详细信息，请参阅 [CMFCFontInfo：： CMFCFontInfo](#cmfcfontinfo)构造函数的 *lpszName* 参数。

## <a name="cmfcfontinfom_strscript"></a><a name="m_strscript"></a> CMFCFontInfo：： m_strScript

与字体关联 (脚本) 的字符集名称。

```
const CString m_strScript;
```

### <a name="remarks"></a>备注

有关详细信息，请参阅 [CMFCFontInfo：： CMFCFontInfo](#cmfcfontinfo)构造函数的 *lpszScript* 参数。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox 类](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox 类](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
