---
description: 了解详细信息： CMFCColorPickerCtrl 类
title: CMFCColorPickerCtrl 类
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: e4363c08af86dee96df1492e9a029414d9902435
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313068"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl 类

`CMFCColorPickerCtrl`类提供用于选择颜色的控件功能。

## <a name="syntax"></a>语法

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCColorPickerCtrl：： CMFCColorPickerCtrl](#cmfccolorpickerctrl)|构造 `CMFCColorPickerCtrl` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCColorPickerCtrl：： GetColor](#getcolor)|检索用户选择的颜色。|
|[CMFCColorPickerCtrl：： GetHLS](#gethls)|检索用户选择的颜色的色调、亮度和饱和度值。|
|[CMFCColorPickerCtrl：： GetHue](#gethue)|检索用户选择的颜色的色调部分。|
|[CMFCColorPickerCtrl：： GetLuminance](#getluminance)|检索用户选择的颜色的亮度部分。|
|[CMFCColorPickerCtrl：： GetSaturation](#getsaturation)|检索用户选择的颜色的饱和度部分。|
|[CMFCColorPickerCtrl：： SelectCellHexagon](#selectcellhexagon)|将当前颜色设置为指定的 RGB 颜色分量或指定的单元格六边形定义的颜色。|
|[CMFCColorPickerCtrl：： SetColor](#setcolor)|将当前颜色设置为指定的 RGB 颜色值。|
|[CMFCColorPickerCtrl：： SetHLS](#sethls)|将当前颜色设置为指定的 HLS 颜色值。|
|[CMFCColorPickerCtrl：： SetHue](#sethue)|更改当前选定颜色的色调部分。|
|[CMFCColorPickerCtrl：： SetLuminance](#setluminance)|更改当前选定颜色的亮度部分。|
|[CMFCColorPickerCtrl：： SetLuminanceBarWidth](#setluminancebarwidth)|设置颜色选取器控件中亮度栏的宽度。|
|[CMFCColorPickerCtrl：： SetOriginalColor](#setoriginalcolor)|设置初始选定的颜色。|
|[CMFCColorPickerCtrl：： SetPalette](#setpalette)|设置当前调色板。|
|[CMFCColorPickerCtrl：： SetSaturation](#setsaturation)|更改当前选定颜色的饱和度部分。|
|[CMFCColorPickerCtrl：： SetType](#settype)|设置要显示的颜色选取器控件的类型。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCColorPickerCtrl：:D rawCursor](#drawcursor)|在显示指向选定颜色的光标之前由框架调用。|

## <a name="remarks"></a>备注

标准颜色是从六角调色板中选择的，并且自定义颜色是从亮度栏中选择的，其中颜色是使用红色/绿色/蓝色表示法或色相/satuaration/亮度表示法指定的。

下图描绘了几个 `CMFCColorPickerCtrl` 对象。

![CMFCColorPickerCtrl 对话框](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl 对话框")

`CMFCColorPickerCtrl`支持两对样式。 HEX 和 HEX_GREYSCALE 样式适用于标准颜色选择。 选取器和亮度样式适用于自定义颜色选择。

执行以下步骤以将控件合并 `CMFCColorPickerCtrl` 到您的对话框中：

1. 如果使用 **ClassWizard**，请将新的按钮控件插入对话框模板 (因为 `CMFCColorPickerCtrl` 该类继承自 `CButton` 类) 。

1. 将与新按钮控件关联的成员变量插入对话框类中。 然后，将变量类型从更改 `CButton` 为 `CMFCColorPickerCtrl` 。

1. `WM_INITDIALOG`为对话框类插入消息处理程序。 在处理程序中，设置控件的类型、调色板和初始选定颜色 `CMFCColorPickerCtrl` 。

## <a name="example"></a>示例

下面的示例演示如何 `CMFCColorPickerCtrl` 使用类中的各种方法配置对象 `CMFCColorPickerCtrl` 。 该示例演示如何设置选取器控件的类型，以及如何设置其颜色、色调、亮度和饱和度。 该示例是 [新控件示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>要求

**标头：** afxcolorpickerctrl

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a> CMFCColorPickerCtrl：： CMFCColorPickerCtrl

构造 `CMFCColorPickerCtrl` 对象。

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a> CMFCColorPickerCtrl：:D rawCursor

在显示指向选定颜色的光标之前由框架调用。

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*rect*<br/>
中指定围绕选定颜色的矩形区域。

### <a name="remarks"></a>备注

需要更改指向所选颜色的光标形状时，请重写此方法。

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a> CMFCColorPickerCtrl：： GetColor

检索用户选择的颜色。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>返回值

选定颜色的 RGB 值。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a> CMFCColorPickerCtrl：： GetHLS

检索用户选择的颜色的色调、亮度和饱和度值。

```cpp
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>parameters

*色相*<br/>
弄一个指针，指向类型为 double 的变量，该变量接收色相信息。

*基色*<br/>
弄一个指针，指向用于接收亮度信息的双精度类型的变量。

*浓度*<br/>
弄一个指针，指向类型为 double 的变量，该变量接收饱和度信息。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a> CMFCColorPickerCtrl：： GetHue

检索用户选择的颜色的色调部分。

```
double GetHue() const;
```

### <a name="return-value"></a>返回值

选定颜色的色调部分。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a> CMFCColorPickerCtrl：： GetLuminance

检索用户选择的颜色的亮度部分。

```
double GetLuminance() const;
```

### <a name="return-value"></a>返回值

选定颜色的亮度分量。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a> CMFCColorPickerCtrl：： GetSaturation

检索用户选择的颜色的饱和度值。

```
double GetSaturation() const;
```

### <a name="return-value"></a>返回值

选定颜色的饱和度部分。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a> CMFCColorPickerCtrl：： SelectCellHexagon

将当前颜色设置为指定的 RGB 颜色分量或指定的单元格六边形定义的颜色。

```cpp
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>parameters

*R*<br/>
中红色成分。

*G*<br/>
中绿色颜色部分。

*B*<br/>
中蓝色颜色组件。

*x*<br/>
中光标的 x 坐标，它指向一个单元格的六边形。

*y*<br/>
中光标的 y 坐标，它指向一个单元格的六边形。

### <a name="return-value"></a>返回值

此方法的第二个重载始终返回 FALSE。

### <a name="remarks"></a>备注

此方法的第一个重载将当前颜色设置为与颜色选择控件的指定红色、绿色和蓝色分量相对应的颜色。

此方法的第二个重载将当前颜色设置为指定光标位置指向的单元格六边形的颜色。

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a> CMFCColorPickerCtrl：： SetColor

将当前颜色设置为指定的 RGB 颜色值。

```cpp
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>parameters

*颜色*<br/>
中RGB 颜色值。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a> CMFCColorPickerCtrl：： SetHLS

将当前颜色设置为指定的 HLS 颜色值。

```cpp
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>parameters

*色相*<br/>
中一个色调值。

*基色*<br/>
中亮度值。

*浓度*<br/>
中饱和度值。

*bInvalidate*<br/>
中若要强制窗口立即更新为新颜色，则为 TRUE;否则为 FALSE。 默认值为 TRUE。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a> CMFCColorPickerCtrl：： SetHue

更改当前选定颜色的色调。

```cpp
void SetHue(double Hue);
```

### <a name="parameters"></a>parameters

*Hue*<br/>
中一个色调值。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a> CMFCColorPickerCtrl：： SetLuminance

更改当前选定颜色的亮度。

```cpp
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>parameters

*亮度*<br/>
中亮度值。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a> CMFCColorPickerCtrl：： SetLuminanceBarWidth

设置颜色选取器控件中亮度栏的宽度。

```cpp
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>parameters

*w*<br/>
中亮度栏的宽度（以像素为单位）。

### <a name="remarks"></a>备注

使用此方法可以调整亮度栏（位于颜色选取器控件的 " **自定义** " 选项卡上）的大小。 *W* 参数指定亮度栏的新宽度。 如果 width 值超过了工作区宽度的四分之三，则将其忽略。

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a> CMFCColorPickerCtrl：： SetOriginalColor

设置初始选定的颜色。

```cpp
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>参数

*ref*<br/>
中RGB 颜色值。

### <a name="remarks"></a>备注

在对颜色选取器控件进行初始化时调用此方法。

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a> CMFCColorPickerCtrl：： SetPalette

设置当前调色板。

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>parameters

*pPalette*<br/>
中指向调色板的指针。

### <a name="remarks"></a>备注

调色板定义颜色选取器控件中显示的颜色的数组。

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a> CMFCColorPickerCtrl：： SetSaturation

更改当前选定颜色的饱和度。

```cpp
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>parameters

*饱和度*<br/>
中饱和度值。

### <a name="remarks"></a>备注

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a> CMFCColorPickerCtrl：： SetType

设置要显示的颜色选取器控件的类型。

```cpp
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>parameters

*colorType*<br/>
中颜色选取器控件类型。

类型由 `CMFCColorPickerCtrl::COLORTYPE` 枚举定义。 可能的类型包括亮度、选取器、HEX 和 HEX_GREYSCALE。 默认类型为 "选择器"。

### <a name="remarks"></a>备注

若要指定颜色选取器控件类型，请在创建 Windows 控件之前调用此方法。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog 类](../../mfc/reference/cmfccolordialog-class.md)
