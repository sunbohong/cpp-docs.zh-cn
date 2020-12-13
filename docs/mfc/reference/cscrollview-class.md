---
description: 了解详细信息： CScrollView 类
title: CScrollView 类
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: 76045f640cf74b650fbbf48dead7ee44c57fbd87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342899"
---
# <a name="cscrollview-class"></a>CScrollView 类

具有滚动功能的 [CView](../../mfc/reference/cview-class.md) 。

## <a name="syntax"></a>语法

```
class CScrollView : public CView
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CScrollView：： CScrollView](#cscrollview)|构造 `CScrollView` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CScrollView：： CheckScrollBars](#checkscrollbars)|指示滚动视图是否具有水平滚动条和垂直滚动条。|
|[CScrollView：： FillOutsideRect](#filloutsiderect)|填充滚动区域外的视图区域。|
|[CScrollView：： GetDeviceScrollPosition](#getdevicescrollposition)|获取设备单位中的当前滚动位置。|
|[CScrollView：： GetDeviceScrollSizes](#getdevicescrollsizes)|获取当前映射模式、总大小以及可滚动视图的行和页大小。 大小为设备单位。|
|[CScrollView：： GetScrollPosition](#getscrollposition)|获取逻辑单元中的当前滚动位置。|
|[CScrollView：： GetTotalSize](#gettotalsize)|获取逻辑单元中滚动视图的总大小。|
|[CScrollView：： ResizeParentToFit](#resizeparenttofit)|导致视图的大小决定其帧的大小。|
|[CScrollView：： ScrollToPosition](#scrolltoposition)|将视图滚动到在逻辑单元中指定的给定点。|
|[CScrollView：： SetScaleToFitSize](#setscaletofitsize)|将滚动视图置于 "缩放到适合" 模式。|
|[CScrollView：： SetScrollSizes](#setscrollsizes)|设置滚动视图的映射模式、总大小以及水平和垂直滚动量。|

## <a name="remarks"></a>备注

您可以 `CView` 通过重写消息映射 [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 和 [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 成员函数，在派生自的任何类中处理标准滚动。 但会 `CScrollView` 将以下功能添加到其 `CView` 功能：

- 它管理窗口和视区的大小和映射模式。

- 它会自动滚动以响应滚动条消息。

- 它会自动滚动，以响应来自键盘、非滚动鼠标或智能鼠标轮的消息。

若要在响应来自键盘的消息时自动滚动，请添加 WM_KEYDOWN 消息，并测试 VK_DOWN、VK_PREV 并调用 [SetScrollPos](/windows/win32/api/winuser/nf-winuser-setscrollpos)。

可以通过重写消息映射 [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) 和 [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) 成员函数来处理鼠标滚轮滚动。 与它们一起 `CScrollView` 使用时，这些成员函数支持 [WM_MOUSEWHEEL](/windows/win32/inputdev/wm-mousewheel)（滚轮旋转消息）的建议行为。

若要利用自动滚动，请从 `CScrollView` 而不是派生视图类 `CView` 。 第一次创建视图时，如果想要基于文档大小计算可滚动视图的大小，请 `SetScrollSizes` 从 [CView：： OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) 或 [cview：： OnUpdate](../../mfc/reference/cview-class.md#onupdate)的重写调用成员函数。  (必须编写自己的代码以查询文档的大小。 有关示例，请参阅 [自由绘制示例](../../overview/visual-cpp-samples.md)。 ) 

对 `SetScrollSizes` 成员函数的调用设置视图的映射模式、滚动视图的总尺寸以及水平和垂直滚动的量。 所有大小均为逻辑单元。 视图的逻辑大小通常是从文档中存储的数据计算的，但在某些情况下，您可能需要指定固定大小。 有关这两种方法的示例，请参阅 [CScrollView：： SetScrollSizes](#setscrollsizes)。

指定要在逻辑单元中水平和垂直滚动的量。 默认情况下，如果用户在滚动框外单击滚动条轴，则 `CScrollView` 滚动 "页"。 如果用户在滚动条的任意一端单击滚动箭头，则 `CScrollView` 滚动到 "行"。 默认情况下，页面的总大小为 1/10;线条的大小为1/10。 通过在成员函数中传递自定义大小来重写这些默认值 `SetScrollSizes` 。 例如，您可以将水平大小设置为总大小的一小部分，将垂直大小设置为当前字体中线条的高度。

`CScrollView`可以自动将视图缩放到当前窗口大小，而不是滚动。 在此模式下，视图没有滚动条，逻辑视图拉伸或收缩，以精确适应窗口的工作区。 若要使用此缩放功能，请调用 [CScrollView：： SetScaleToFitSize](#setscaletofitsize)。  (调用 `SetScaleToFitSize` 或 `SetScrollSizes` ，而不是同时调用。 ) 

在 `OnDraw` 调用派生视图类的成员函数之前， `CScrollView` 会自动调整 `CPaintDC` 其传递到的设备上下文对象的视口原点 `OnDraw` 。

若要调整滚动窗口的视区原点，请 `CScrollView` 重写 [CView：： OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)。 此调整在 `CPaintDC` 传递到的设备上下文中是自动进行的 `CScrollView` `OnDraw` ，但你必须 `CScrollView::OnPrepareDC` 为你使用的任何其他设备上下文 `CClientDC` （如）调用。 可以重写 `CScrollView::OnPrepareDC` 以设置笔、背景色和其他绘图属性，但可以调用基类来进行缩放。

滚动条可在相对于视图的三个位置出现，如以下情况所示：

- 可以使用 WS_HSCROLL 和 WS_VSCROLL[Windows 样式](../../mfc/reference/styles-used-by-mfc.md#window-styles)为视图设置标准窗口样式滚动条。

- 还可以将滚动条控件添加到包含该视图的框架，在这种情况下，框架会将 WM_HSCROLL 和 WM_VSCROLL 消息从框架窗口转发到当前活动视图。

- 该框架还将滚动消息从 `CSplitterWnd` 拆分器控件转发到当前活动的拆分器窗格 (视图) 。 当使用共享滚动条放置在 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) 中时， `CScrollView` 对象将使用共享的滚动条，而不是创建自己的滚动条。

有关使用的详细信息 `CScrollView` ，请参阅 [文档/视图体系结构](../../mfc/document-view-architecture.md) 和 [MFC 中可用的派生视图类](../../mfc/derived-view-classes-available-in-mfc.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a> CScrollView：： CheckScrollBars

调用此成员函数以确定滚动视图是否具有水平和垂直条。

```cpp
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>parameters

*bHasHorzBar*<br/>
指示应用程序具有水平滚动条。

*bHasVertBar*<br/>
指示应用程序具有垂直滚动条。

## <a name="cscrollviewcscrollview"></a><a name="cscrollview"></a> CScrollView：： CScrollView

构造 `CScrollView` 对象。

```
CScrollView();
```

### <a name="remarks"></a>备注

在 `SetScrollSizes` `SetScaleToFitSize` 滚动视图可用之前，必须调用或。

## <a name="cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a> CScrollView：： FillOutsideRect

调用 `FillOutsideRect` 以填充显示在滚动区域外的视图区域。

```cpp
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
要在其中完成填充的设备上下文。

*pBrush*<br/>
要填充区域的画笔。

### <a name="remarks"></a>备注

`FillOutsideRect`在滚动视图的 `OnEraseBkgnd` 处理程序函数中使用，以防止过度进行后台重画。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

## <a name="cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a> CScrollView：： GetDeviceScrollPosition

`GetDeviceScrollPosition`如果需要滚动条中滚动框的当前水平和垂直位置，请调用。

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>返回值

水平和垂直位置 (作为对象滚动框的设备单位) `CPoint` 。

### <a name="remarks"></a>备注

此坐标对对应于文档中滚动视图的左上角的位置。 这适用于将鼠标设备位置偏移到滚动查看设备位置。

`GetDeviceScrollPosition` 返回以设备单位表示的值。 如果希望使用逻辑单元，请 `GetScrollPosition` 改用。

## <a name="cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a> CScrollView：： GetDeviceScrollSizes

`GetDeviceScrollSizes` 获取当前映射模式、总大小以及可滚动视图的行和页大小。

```cpp
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>parameters

*nMapMode*<br/>
返回此视图的当前映射模式。 有关可能值的列表，请参见 `SetScrollSizes`。

*sizeTotal*<br/>
返回滚动视图的当前总大小（以设备单位为单位）。

*sizePage*<br/>
返回当前水平和垂直的量，以响应滚动条轴中的鼠标单击的方向滚动。 `cx`成员包含水平量。 `cy`成员包含垂直量。

*sizeLine*<br/>
返回当前的水平和垂直量，以响应滚动箭头中的鼠标单击的方向滚动。 `cx`成员包含水平量。 `cy`成员包含垂直量。

### <a name="remarks"></a>备注

大小为设备单位。 很少调用此成员函数。

## <a name="cscrollviewgetscrollposition"></a><a name="getscrollposition"></a> CScrollView：： GetScrollPosition

`GetScrollPosition`如果需要滚动条中滚动框的当前水平和垂直位置，请调用。

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>返回值

水平和垂直位置 (以对象的形式) 滚动框的逻辑单元中 `CPoint` 。

### <a name="remarks"></a>备注

此坐标对对应于文档中滚动视图的左上角的位置。

`GetScrollPosition` 返回逻辑单元中的值。 如果需要设备单位，请改用 `GetDeviceScrollPosition` 。

## <a name="cscrollviewgettotalsize"></a><a name="gettotalsize"></a> CScrollView：： GetTotalSize

调用 `GetTotalSize` 以检索滚动视图的当前水平和垂直大小。

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>返回值

以逻辑单元表示的滚动视图的总大小。 水平大小位于 `cx` 返回值的成员中 `CSize` 。 垂直大小在 `cy` 成员中。

## <a name="cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a> CScrollView：： ResizeParentToFit

调用 `ResizeParentToFit` 以让你的视图的大小决定其框架窗口的大小。

```cpp
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>parameters

*bShrinkOnly*<br/>
要执行的调整大小的类型。 默认值为 TRUE，则在适当的情况下收缩框架窗口。 对于大型视图或小型框架窗口，将仍然显示滚动条。 如果值为 FALSE，则会使视图始终精确地调整框架窗口的大小。 这可能有点危险，因为框架窗口可能会太大而无法容纳在多文档界面中 (MDI) 框架窗口或屏幕。

### <a name="remarks"></a>备注

对于 MDI 子框架窗口中的视图，建议使用此项。 用于 `ResizeParentToFit` `OnInitialUpdate` 派生类的处理程序函数 `CScrollView` 。 有关此成员函数的示例，请参阅 [CScrollView：： SetScrollSizes](#setscrollsizes)。

`ResizeParentToFit` 假设已设置视图窗口的大小。 如果在调用时未设置视图窗口大小 `ResizeParentToFit` ，则将获得一个断言。 若要确保不会发生这种情况，请在调用之前进行以下调用 `ResizeParentToFit` ：

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a> CScrollView：： ScrollToPosition

调用 `ScrollToPosition` 以滚动到视图中的给定点。

```cpp
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>parameters

*pt*<br/>
要滚动到的点，单位为逻辑单元。 `x`成员必须是大于或等于 0 (的正值，最大值为视图) 的总大小。 `y`MM_TEXT 映射模式时，成员也是如此。 `y`除 MM_TEXT 之外，成员在映射模式下为负。

### <a name="remarks"></a>备注

视图将滚动，这一点位于窗口的左上角。 如果调整了视图的大小，则不得调用此成员函数。

## <a name="cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a> CScrollView：： SetScaleToFitSize

`SetScaleToFitSize`当要将视区大小自动缩放到当前窗口大小时，请调用。

```cpp
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>parameters

*sizeTotal*<br/>
视图要缩放到的水平和垂直大小。 滚动视图的大小以逻辑单位进行度量。 水平大小包含在 `cx` 成员中。 垂直大小包含在 `cy` 成员中。 `cx`和 `cy` 必须大于或等于0。

### <a name="remarks"></a>备注

如果使用滚动条，则任何时候都只能显示部分逻辑视图。 但对于缩放功能，视图没有滚动条，逻辑视图将进行拉伸或收缩，以精确适应窗口的工作区。 调整窗口大小时，视图会根据窗口的大小以新的比例绘制数据。

通常会将对的调用置于 `SetScaleToFitSize` 视图的成员函数的重写中 `OnInitialUpdate` 。 如果不想进行自动缩放，请调用 `SetScrollSizes` 成员函数。

`SetScaleToFitSize` 可用于实现 "缩放到合适大小" 操作。 使用重新 `SetScrollSizes` 初始化滚动。

`SetScaleToFitSize` 假设已设置视图窗口的大小。 如果在调用时未设置视图窗口大小 `SetScaleToFitSize` ，则将获得一个断言。 若要确保不会发生这种情况，请在调用之前进行以下调用 `SetScaleToFitSize` ：

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a> CScrollView：： SetScrollSizes

`SetScrollSizes`要更新视图时调用。

```cpp
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>parameters

*nMapMode*<br/>
要为此视图设置的映射模式。 可能的值包括：

|映射模式|逻辑单元|正 y 轴扩展 .。。|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 像素|钮|
|MM_HIMETRIC|0.01 毫米|拉|
|MM_TWIPS|1/1440|拉|
|MM_HIENGLISH|0.001|拉|
|MM_LOMETRIC|0.1 毫米|拉|
|MM_LOENGLISH|0.01|拉|

所有这些模式都由 Windows 定义。 两种标准映射模式 MM_ISOTROPIC 和 MM_ANISOTROPIC 不用于 `CScrollView` 。 类库提供 `SetScaleToFitSize` 用于将视图缩放到窗口大小的成员函数。 上表中的第三列描述坐标方向。

*sizeTotal*<br/>
滚动视图的总大小。 `cx`成员包含水平区。 `cy`成员包含垂直区。 大小为逻辑单元。 `cx`和 `cy` 必须大于或等于0。

*sizePage*<br/>
在每个方向上滚动的水平和垂直量，用于响应滚动条轴中的鼠标单击。 `cx`成员包含水平量。 `cy`成员包含垂直量。

*sizeLine*<br/>
在每个方向上滚动的水平和垂直量，用于响应滚动箭头中的鼠标单击。 `cx`成员包含水平量。 `cy`成员包含垂直量。

### <a name="remarks"></a>备注

在成员函数的重写中调用该 `OnUpdate` 函数，以便在（例如，文档最初显示或更改大小时）调整滚动特性。

通常，通过调用 `GetMyDocSize` 与派生文档类一起提供的文档成员函数（可能称为），可以从视图的关联文档中获得大小信息。 下面的代码演示了这种方法：

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

或者，有时你可能需要设置固定大小，如以下代码所示：

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

您必须将映射模式设置为任何 Windows 映射模式（MM_ISOTROPIC 或 MM_ANISOTROPIC 除外）。 如果要使用不受约束的映射模式，请调用 `SetScaleToFitSize` 成员函数而不是 `SetScrollSizes` 。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>请参阅

[MFC 示例 DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView 类](../../mfc/reference/cview-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CView 类](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd 类](../../mfc/reference/csplitterwnd-class.md)
