---
description: 了解详细信息： CMFCRibbonProgressBar 类
title: CMFCRibbonProgressBar 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: b4e91a604386a57aa7cac59294c569635583304c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321756"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar 类

实现用于直观指示较长操作进度的控件。

## <a name="syntax"></a>语法

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|构造并初始化一个 `CMFCRibbonProgressBar` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonProgressBar：： GetPos](#getpos)|返回当前进度。|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|返回当前范围的最大值。|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|返回当前范围的最小值。|
|[CMFCRibbonProgressBar：： GetRegularSize](#getregularsize)|返回功能区元素的常规大小。  (重写 [CMFCRibbonBaseElement：： GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)。 ) |
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|指定进度栏是否处于无限大模式下工作。|
|[CMFCRibbonProgressBar：： OnDraw](#ondraw)|由框架调用以绘制功能区元素。  (重写 [CMFCRibbonBaseElement：： OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)。 ) |
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|将进度栏设置为在无限大模式下工作。|
|[CMFCRibbonProgressBar：： SetPos](#setpos)|设置当前进度。|
|[CMFCRibbonProgressBar：： SetRange](#setrange)|设置最小值和最大值。|

## <a name="remarks"></a>备注

`CMFCRibbonProgressBar`可在两种模式下运行：常规和无限大。 在常规模式下，进度栏是从左到右填充的，在达到最大值时停止。 在无限大模式下，进度栏会从最小值重复填充到最大值。 您可以使用无限大模式指示操作正在进行，但完成时间是未知的。

## <a name="example"></a>示例

下面的示例演示了如何使用 `CMFCRibbonProgressBar` 类中的各种方法。 该示例演示了如何将进度栏设置为在无限模式下工作 (其中操作的完成时间未知) ，设置进度栏的最小值和最大值，并设置进度栏的当前位置。 此代码片段是 [MS Office 2007 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxRibbonProgressBar

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a> CMFCRibbonProgressBar::CMFCRibbonProgressBar

构造并初始化 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) 对象。

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>parameters

*nID*<br/>
中指定功能区进度栏的命令 ID。

*nWidth*<br/>
中指定功能区进度栏的宽度（以像素为单位）。

*nHeight*<br/>
中指定功能区进度栏的高度（以像素为单位）。

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a> CMFCRibbonProgressBar：： GetPos

返回进度栏的当前位置。

```
int GetPos () const;
```

### <a name="return-value"></a>返回值

一个值，该值表示进度栏的当前位置。

### <a name="remarks"></a>备注

要设置的范围必须在 [CMFCRibbonProgressBar：： SetRange](#setrange) 方法指定的范围内。

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a> CMFCRibbonProgressBar::GetRangeMax

返回进度栏的当前最大值。

```
int GetRangeMax() const;
```

### <a name="return-value"></a>返回值

当前范围的最大值。

### <a name="remarks"></a>备注

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a> CMFCRibbonProgressBar::GetRangeMin

返回进度栏的当前最小范围值。

```
int GetRangeMin() const;
```

### <a name="return-value"></a>返回值

当前范围的最小值。

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a> CMFCRibbonProgressBar：： GetRegularSize

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a> CMFCRibbonProgressBar::IsInfiniteMode

指定进度栏是否处于无限大模式下工作。

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>返回值

如果进度栏处于无限大模式，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

在无限大模式下，进度栏会从最小值重复到最大值。 您可以使用无限大模式指示操作正在进行，但完成时间是未知的。

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a> CMFCRibbonProgressBar：： OnDraw

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a> CMFCRibbonProgressBar::SetInfiniteMode

将进度栏设置为在无限大模式下工作。

```cpp
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>parameters

*bSet*<br/>
中若要指定进度栏处于无限大模式，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

通常，如果进度栏处于无限大模式，则表示用户正在进行操作，但完成时间未知。 因此，进度栏会从最小值重复到最大值。

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a> CMFCRibbonProgressBar：： SetPos

设置进度栏的当前位置。

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>parameters

*nPos*<br/>
中指定进度栏的设置位置。

*bRedraw*<br/>
中指定是否应重绘进度栏。

### <a name="remarks"></a>备注

要设置的范围必须在 [CMFCRibbonProgressBar：： SetRange](#setrange) 方法指定的范围内。

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a> CMFCRibbonProgressBar：： SetRange

设置进度栏的最小值和最大值。

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>parameters

*nMin*<br/>
中指定范围的最小值。

*N 每天*<br/>
中指定范围的最大值。

### <a name="remarks"></a>备注

使用此方法可以通过设置最小值和最大值来定义进度栏的范围。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement 类](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)
