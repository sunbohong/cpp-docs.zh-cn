---
description: 了解详细信息： CMFCToolBarFontSizeComboBox 类
title: CMFCToolBarFontSizeComboBox 类
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: a355e62f2ef538372d70b9b2b393bc16bff2ef4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331750"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox 类

包含组合框控件的工具栏按钮，该控件使用户能够选择字体大小。

## <a name="syntax"></a>语法

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|构造 `CMFCToolBarFontSizeComboBox` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|返回所选字体大小（以缇为单位）。|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|用指定字体的所有支持的字号填充组合框列表。|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|设置字体大小（以缇为单位）。|

## <a name="remarks"></a>备注

可以将 `CMFCToolBarFontSizeComboBox` 对象与 [CMFCToolBarFontComboBox 类](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 对象一起使用，以使用户能够选择字体和字体大小。

您可以将 "字体大小" 组合框按钮添加到工具栏中，就像添加字体组合框按钮一样。 有关详细信息，请参阅 [CMFCToolBarFontComboBox 类](../../mfc/reference/cmfctoolbarfontcombobox-class.md)。

当用户在对象中选择新字体时 `CMFCToolBarFontComboBox` ，可以使用 [CMFCToolBarFontSizeComboBox：： RebuildFontSizes](#rebuildfontsizes) 方法填充字体大小组合框，该组合框中的字体大小受支持。

## <a name="example"></a>示例

下面的示例演示如何使用类中的各种方法 `CMFCToolBarFontSizeComboBox` 配置 `CMFCToolBarFontSizeComboBox` 对象。 该示例演示了如何从文本框中检索字号（以缇为单位），在 "字体大小" 组合框中填充给定字体的所有有效大小，并以缇为单位指定字体大小。 此代码片段属于 [Word Pad 示例](../../overview/visual-cpp-samples.md)。

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>要求

**标头：** afxtoolbarfontcombobox

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a> CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

构造 `CMFCToolBarFontSizeComboBox` 对象。

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a> CMFCToolBarFontSizeComboBox::GetTwipSize

从字号组合框的文本框中检索字号（以缇为单位）。

```
int GetTwipSize() const;
```

### <a name="return-value"></a>返回值

如果返回值为正，则它是字号（以缇为单位）。 如果组合框的文本框为空，则为-1。 如果发生错误，则为-2。

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a> CMFCToolBarFontSizeComboBox::RebuildFontSizes

使用给定字体的所有有效大小填充字体大小组合框。

```cpp
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>parameters

*strFontName*<br/>
中指定字体名称。

### <a name="remarks"></a>备注

如果要在字体组合框中的选定内容与字体大小组合框（如 [CMFCToolBarFontComboBox 类](../../mfc/reference/cmfctoolbarfontcombobox-class.md)）之间进行同步，请调用此函数。

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a> CMFCToolBarFontSizeComboBox::SetTwipSize

将指定大小 (以缇为单位舍入为最接近的大小（以磅为) 单位），然后将组合框中的选定大小设置为该值。

```cpp
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>parameters

*nSize*<br/>
中指定要设置的字号 (以缇) 。

### <a name="remarks"></a>备注

稍后可通过调用 [CMFCToolBarFontSizeComboBox：： GetTwipSize](#gettwipsize) 方法检索以前的有效字体大小。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton 类](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton 类](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo 类](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar：： ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[演练：将控件置于工具栏上](../../mfc/walkthrough-putting-controls-on-toolbars.md)
