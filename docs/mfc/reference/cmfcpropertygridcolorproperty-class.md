---
description: 了解详细信息： CMFCPropertyGridColorProperty 类
title: CMFCPropertyGridColorProperty 类
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
ms.openlocfilehash: 7673044a149dc1b5171167ed0854918434651dc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334702"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty 类

`CMFCPropertyGridColorProperty` 类支持用于打开颜色选择对话框的属性列表控件项。

## <a name="syntax"></a>语法

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|构造 `CMFCPropertyGridColorProperty` 对象。|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|启用颜色选择对话框上的 " *自动* " 按钮。  (将标准 "自动" 按钮标记为 " **自动**"。 ) |
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|启用 "颜色选择" 对话框中的 " *其他* " 按钮。  ("其他标准" 按钮标记为 " **更多颜色**"。 ) |
|`CMFCPropertyGridColorProperty::FormatProperty`|设置属性值的文本表示形式的格式。  (重写 [CMFCPropertyGridProperty：： FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)。 ) |
|[CMFCPropertyGridColorProperty：： GetColor](#getcolor)|获取属性的当前颜色。|
|`CMFCPropertyGridColorProperty::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|`CMFCPropertyGridColorProperty::OnClickButton`|当用户单击属性中包含的按钮时，由框架调用。  (重写 [CMFCPropertyGridProperty：： OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)。 ) |
|`CMFCPropertyGridColorProperty::OnDrawValue`|由框架调用以显示属性值。  (重写 [CMFCPropertyGridProperty：： OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue)。 ) |
|`CMFCPropertyGridColorProperty::OnEdit`|当用户要修改属性值时由框架调用。  (重写 [CMFCPropertyGridProperty：： OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit)。 ) |
|`CMFCPropertyGridColorProperty::OnUpdateValue`|当可编辑属性值已更改时由框架调用。  (重写 [CMFCPropertyGridProperty：： OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue)。 ) |
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|设置属性的新颜色。|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|指定当前颜色属性网格中的列数。|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|设置可编辑属性的原始值。|

## <a name="remarks"></a>备注

`CMFCPropertyGridColorProperty` 类支持可添加到属性列表控件的颜色属性。 有关详细信息，请参阅 [CMFCPropertyGridCtrl 类](../../mfc/reference/cmfcpropertygridctrl-class.md)。

## <a name="example"></a>示例

下面的示例演示如何构造 `CMFCPropertyGridColorProperty` 类的对象，以及如何使用 `CMFCPropertyGridColorProperty` 类的各种方法来配置此对象。 下面的代码介绍如何启用“自动”按钮和“其他”按钮，以及如何设置颜色和列数。 此示例是 [新控件示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>要求

**标头：** afxpropertygridctrl

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a> CMFCPropertyGridColorProperty：： CMFCPropertyGridColorProperty

构造 `CMFCPropertyGridColorProperty` 对象。

```
CMFCPropertyGridColorProperty(
    const CString& strName,
    const COLORREF& color,
    CPalette* pPalette = NULL,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0);
```

### <a name="parameters"></a>parameters

*strName*<br/>
中属性的名称。

*color*<br/>
中属性的颜色值。

*pPalette*<br/>
中指向颜色调色板的指针。 默认值为 NULL。

*lpszDescr*<br/>
中属性说明。 默认值为 NULL。

*dwData*<br/>
中应用程序特定的数据，例如一个整数或指向与属性关联的其他数据的指针。 默认值为 0。

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCPropertyGridColorProperty：： EnableAutomaticButton

启用颜色选择对话框上的 " *自动* " 按钮。  (将标准 "自动" 按钮标记为 " **自动**"。 ) 

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中"自动" 按钮的标签文本。

*colorAutomatic*<br/>
中自动 (默认) 颜色的 RGB 颜色值。

*bEnable*<br/>
中若要启用自动按钮，则为 TRUE;否则为 FALSE。 默认值为 TRUE。

### <a name="remarks"></a>备注

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a> CMFCPropertyGridColorProperty：： EnableOtherButton

启用 "颜色选择" 对话框中的 " *其他* " 按钮。  ("其他标准" 按钮标记为 " **更多颜色**"。 ) 

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中其他按钮的标签文本。

*bAltColorDlg*<br/>
中若要显示对话框，则为 TRUE `CMFCColorDialog` ;若要显示标准颜色选择对话框，则为 FALSE。 默认值为 TRUE。

*bEnable*<br/>
中若要显示另一个按钮，则为 TRUE;否则为 FALSE。  默认值为 TRUE。

### <a name="remarks"></a>备注

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a> CMFCPropertyGridColorProperty：： GetColor

获取属性的当前颜色。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>返回值

RGB 颜色值。

### <a name="remarks"></a>备注

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a> CMFCPropertyGridColorProperty：： SetColor

设置属性的新颜色。

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>parameters

*color*<br/>
中RGB 颜色值。

### <a name="remarks"></a>备注

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a> CMFCPropertyGridColorProperty：： SetColumnsNumber

指定当前颜色属性网格中的列数。

```cpp
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>parameters

*nColumnsNumber*<br/>
中"颜色" 属性网格中的首选列数。

### <a name="remarks"></a>备注

此方法设置 `m_nColumnsNumber` 受保护的数据成员的值。

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a> CMFCPropertyGridColorProperty：： SetOriginalValue

设置可编辑属性的原始值。

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>parameters

*varValue*<br/>
中一个值。

### <a name="remarks"></a>备注

使用 [CMFCPropertyGridProperty：： ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) 方法重置已编辑属性的原始值。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl 类](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty 类](../../mfc/reference/cmfcpropertygridproperty-class.md)
