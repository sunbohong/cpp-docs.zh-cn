---
description: 了解详细信息： CMFCRibbonSlider 类
title: CMFCRibbonSlider 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
ms.openlocfilehash: d125afdf961d97c0501742acdc75d7802c7e104d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321729"
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider 类

`CMFCRibbonSlider`类实现可添加到功能区栏或功能区状态栏的滑块控件。 功能区滑块控件类似于显示在 Office 2007 应用程序中的缩放滑块。

## <a name="syntax"></a>语法

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|构造和初始化功能区滑块控件。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonSlider：： GetPos](#getpos)|返回滑块控件的当前位置。|
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|返回滑块的最大值。|
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|返回滑块的最小值。|
|[CMFCRibbonSlider：： GetRegularSize](#getregularsize)|返回功能区元素的常规大小。  (重写 [CMFCRibbonBaseElement：： GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)。 ) |
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|返回滑块控件的缩放增量的大小。|
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|指定滑块是否具有缩放按钮。|
|[CMFCRibbonSlider：： OnDraw](#ondraw)|由框架调用以绘制功能区元素。  (重写 [CMFCRibbonBaseElement：： OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)。 ) |
|[CMFCRibbonSlider：： SetPos](#setpos)|设置滑块控件的当前位置。|
|[CMFCRibbonSlider：： SetRange](#setrange)|通过设置最小值和最大值来指定滑块控件的范围。|
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|显示或隐藏缩放按钮。|
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|设置滑块控件的缩放增量的大小。|

## <a name="remarks"></a>备注

您可以使用 `SetRange` 方法为滑块配置缩放增量范围。 您可以通过使用方法来设置滑块的当前位置 `SetPos` 。

通过使用方法，可以在滑块控件的左侧和右侧显示圆形缩放按钮 `SetZoomButtons` 。 默认情况下，滑块为水平方向，左缩放按钮显示一个减号，右侧缩放按钮显示一个加号。

`SetZoomIncrement`当用户单击缩放按钮时，方法定义从当前位置添加或减去的增量。

## <a name="example"></a>示例

下面的示例演示如何使用类中的各种方法 `CMFCRibbonSlider` 来设置滑块的属性。 该示例演示了如何构造 `CMFCRibbonSlider` 对象、显示缩放按钮、设置滑块控件的当前位置，并为滑块控件设置值的范围。

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>要求

**标头：** afxribbonslider

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a> CMFCRibbonSlider::CMFCRibbonSlider

构造功能区滑块。

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>parameters

*nID*<br/>
中滑块 ID。

[in]。 *nWidth* 滑块宽度（像素）。

### <a name="remarks"></a>备注

构造一个在添加滑块的面板类别中 *nWidth* 像素宽的功能区滑块。 默认情况下，滑块为水平滑块。

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a> CMFCRibbonSlider：： GetPos

返回滑块控件的当前位置。

```
int GetPos() const;
```

### <a name="return-value"></a>返回值

滑块控件的当前位置，它是相对于滑块开头的位置。

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a> CMFCRibbonSlider::GetRangeMax

获取滑块可以在滑块控件上行进的滑块的最大增量。

```
int GetRangeMax() const;
```

### <a name="return-value"></a>返回值

滑块可以在滑块控件上行进的滑块的最大增量。

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a> CMFCRibbonSlider::GetRangeMin

返回滑块可以在滑块控件上行进的最小增量。

```
int GetRangeMin() const;
```

### <a name="return-value"></a>返回值

滑块可以在滑块控件上行进的最小增量。

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a> CMFCRibbonSlider：： GetRegularSize

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a> CMFCRibbonSlider::GetZoomIncrement

获取滑块控件的缩放增量。

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>返回值

滑块控件的缩放增量。

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a> CMFCRibbonSlider::HasZoomButtons

指定滑块是否具有缩放按钮。

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>返回值

如果滑块具有缩放按钮，则为 TRUE;否则为 FALSE。

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a> CMFCRibbonSlider：： OnDraw

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a> CMFCRibbonSlider：： SetPos

设置滑块控件的当前位置。

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>parameters

*nPos*<br/>
中指定要为滑块设置的位置。 位置相对于滑块的开头。

*bRedraw*<br/>
中如果为 TRUE，则将重绘滑块。

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a> CMFCRibbonSlider：： SetRange

为滑块控件设置值的范围。

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>parameters

*nMin*<br/>
中指定滑块控件的最小值。

*N 每天*<br/>
中指定滑块控件的最大值。

### <a name="remarks"></a>备注

通过设置最小值和最大值，为滑块控件指定值的范围。

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a> CMFCRibbonSlider::SetZoomButtons

显示或隐藏缩放按钮。

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>parameters

[in]。 *bSet* 如果显示缩放按钮，则为 TRUE;如果隐藏，则为 FALSE。

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a> CMFCRibbonSlider::SetZoomIncrement

设置滑块控件的缩放增量。

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>parameters

*nZoomIncrement*<br/>
中指定滑块控件的缩放增量。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement 类](../../mfc/reference/cmfcribbonbaseelement-class.md)
