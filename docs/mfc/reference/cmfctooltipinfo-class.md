---
description: 了解详细信息： CMFCToolTipInfo 类
title: CMFCToolTipInfo 类
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: 06ceca500ad92d5f3a27e2740a298d9c1bbfe1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143424"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo 类

存储有关工具提示视觉外观的信息。

## <a name="syntax"></a>语法

```
class CMFCToolTipInfo
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCToolTipInfo::operator=](#operator_eq)||

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCToolTipInfo：： m_bBalloonTooltip](#m_bballoontooltip)|指示工具提示是否具有气球外观的布尔变量。|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|指示工具提示标签是否以粗体显示的布尔变量。|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|指示工具提示是否包含说明的布尔变量。|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|指示工具提示是否包含图标的布尔变量。|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|指示分隔符是否显示在工具提示标签和工具提示说明之间的布尔变量。|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|指示工具提示是否具有圆角的布尔变量。|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|布尔变量，指示工具提示的外观是否应由可视化管理器控制 (参阅 [CMFCVisualManager 类](../../mfc/reference/cmfcvisualmanager-class.md)) 。|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|工具提示边框的颜色。|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|工具提示背景的颜色。|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|工具提示中渐变填充的颜色。|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|工具提示中的文本颜色。|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|工具提示中渐变填充的角度。|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|工具提示中说明的最大可能宽度（以像素为单位）。|

## <a name="remarks"></a>备注

结合使用 [CMFCToolTipCtrl 类](../../mfc/reference/cmfctooltipctrl-class.md)、 `CMFCToolTipInfo` 和 [CTooltipManager 类](../../mfc/reference/ctooltipmanager-class.md) ，在应用程序中实现自定义的工具提示。 有关如何使用这些 tooltip 类的示例，请参阅 [CMFCToolTipCtrl 类](../../mfc/reference/cmfctooltipctrl-class.md) 主题。

## <a name="example"></a>示例

下面的示例演示了如何在 `CMFCToolTipInfo` 类中设置多个成员变量的值的方法。

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>要求

**标头：** afxtooltipctrl

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a> CMFCToolTipInfo：： m_bBalloonTooltip

指定所有工具提示的显示样式。

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>备注

如果为 TRUE，则表示工具提示使用了气球样式，FALSE 表示工具提示使用矩形样式。

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a> CMFCToolTipInfo：： m_bBoldLabel

指定工具提示文本的字体是否为粗体。

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>备注

将此成员设置为 TRUE 以显示带有粗体的工具提示文本，或设置为 FALSE 以显示带有非粗体字体的工具提示标签。

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a> CMFCToolTipInfo：： m_bDrawDescription

指定每个工具提示是否显示说明文本。

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>备注

将此成员设置为 TRUE 以显示说明，或设置为 FALSE 以隐藏说明。 可以通过调用[CMFCToolTipCtrl：： SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)在工具提示上指定描述

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a> CMFCToolTipInfo：： m_bDrawIcon

指定是否所有工具提示都显示图标。

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>备注

将此成员设置为 TRUE 可在每个工具提示上显示一个图标，或设置为 FALSE 以显示无图标的工具提示。

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a> CMFCToolTipInfo：： m_bDrawSeparator

指定每个工具提示是否在其标签与其说明之间具有分隔符。

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>备注

将此成员设置为 TRUE 可在 tooltip 标签和说明之间显示分隔符; 如果为 FALSE，则显示无分隔符的工具提示。

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a> CMFCToolTipInfo：： m_bRoundedCorners

指定所有工具提示是否都具有圆角。

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>备注

将此成员设置为 TRUE 可在工具提示上显示圆角，或设置为 FALSE 可在工具提示上显示矩形角。

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a> CMFCToolTipInfo：： m_clrBorder

指定所有工具提示的边框颜色。

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a> CMFCToolTipInfo：： m_clrFill

指定工具提示背景的颜色。

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>备注

如果 [CMFCToolTipInfo：： m_clrFillGradient](#m_clrfillgradient) 为-1，则工具提示的背景色为 `m_clrFill` 。 否则， `m_clrFill` 指定渐变开头的颜色，并 `m_clrFillGradient` 指定渐变末尾的颜色。 [CMFCToolTipInfo：： m_nGradientAngle](#m_ngradientangle) 确定渐变的方向。

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a> CMFCToolTipInfo：： m_clrFillGradient

指定工具提示的渐变背景的结束颜色。

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>备注

如果 `m_clrFillGradient` 为-1，则没有梯度。 否则，渐变初始颜色由 [CMFCToolTipInfo：： m_clrFill](#m_clrfill) 指定，并且渐变完成颜色由指定 `m_clrFillGradient` 。 [CMFCToolTipInfo：： m_nGradientAngle](#m_ngradientangle) 确定渐变的方向。

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a> CMFCToolTipInfo：： m_clrText

指定所有工具提示的文本颜色。

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a> CMFCToolTipInfo：： m_nGradientAngle

指定在工具提示背景上绘制渐变的角度。

```
int m_nGradientAngle;
```

### <a name="remarks"></a>备注

`m_nGradientAngle` 指定工具提示背景上的渐变与水平的偏移量（以度为单位）。 如果 `m_nGradientAngle` 为0，则按从左到右的渐变绘制。 如果 `m_nGradientAngle` 介于1到360之间，则渐变将按该度数顺时针旋转。 如果 `m_nGradientAngle` 为-1 （默认值），则按从上到下的顺序绘制渐变。 这与设置为90的情况相同 `m_nGradientAngle` 。

[CMFCToolTipInfo：： m_clrFill](#m_clrfill) `clrFill` 指定渐变开头的颜色， [CMFCToolTipInfo：： m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` 指定渐变末尾的颜色。 如果 `m_clrFillGradient` 为-1，则没有梯度。

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a> CMFCToolTipInfo：： m_nMaxDescrWidth

指定它在每个工具提示中显示的最大宽度。 如果描述宽度超过指定的值，则文本会换行。

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a> CMFCToolTipInfo：： m_bVislManagerTheme

指定应用程序的可视化管理器是否控制所有工具提示的外观。

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>备注

如果 `m_bVislManagerTheme` 为 TRUE，则每个工具提示在应用程序的可视化管理器中请求一个新的 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) ，然后将其显示在屏幕上，并使用该对象中的值来确定其外观。 将忽略 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) 的其他成员。

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a> CMFCToolTipInfo：： operator =

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>parameters

中 *src*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CTooltipManager 类](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipCtrl 类](../../mfc/reference/cmfctooltipctrl-class.md)
