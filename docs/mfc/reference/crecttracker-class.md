---
description: 了解详细信息： CRectTracker 类
title: CRectTracker 类
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: 8406b6b45a99ca2e1816cb650f243fcea2db8ddc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343015"
---
# <a name="crecttracker-class"></a>CRectTracker 类

允许在不同的 fashions 中显示、移动和调整项的大小。

## <a name="syntax"></a>语法

```
class CRectTracker
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CRectTracker：： CRectTracker](#crecttracker)|构造 `CRectTracker` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CRectTracker：： AdjustRect](#adjustrect)|当调整矩形大小时调用。|
|[CRectTracker：:D raw](#draw)|呈现矩形。|
|[CRectTracker：:D rawTrackerRect](#drawtrackerrect)|绘制对象的边框时调用 `CRectTracker` 。|
|[CRectTracker：： GetHandleMask](#gethandlemask)|调用以获取 `CRectTracker` 项的大小调整句柄的掩码。|
|[CRectTracker：： GetTrueRect](#gettruerect)|返回矩形的宽度和高度，包括调整大小控点。|
|[CRectTracker：： System.windows.media.visualtreehelper.hittest](#hittest)|返回与对象相关的光标当前位置 `CRectTracker` 。|
|[CRectTracker：： NormalizeHit](#normalizehit)|规范化命中测试代码。|
|[CRectTracker：： OnChangedRect](#onchangedrect)|在对矩形进行调整大小或移动后调用。|
|[CRectTracker：： SetCursor](#setcursor)|根据游标在矩形上的位置来设置光标。|
|[CRectTracker：： Track](#track)|允许用户操作矩形。|
|[CRectTracker：： TrackRubberBand](#trackrubberband)|允许用户 "带区" 选定内容。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CRectTracker：： m_nHandleSize](#m_nhandlesize)|确定调整大小控点的大小。|
|[CRectTracker：： m_nStyle](#m_nstyle)|跟踪器 () 当前样式。|
|[CRectTracker：： m_rect](#m_rect)|矩形的当前位置 (以像素为单位) 。|
|[CRectTracker：： m_sizeMin](#m_sizemin)|确定矩形的最小宽度和高度。|

## <a name="remarks"></a>备注

`CRectTracker` 没有基类。

尽管 `CRectTracker` 类旨在允许用户使用图形界面与 OLE 项进行交互，但它的使用并不局限于启用 ole 的应用程序。 它可以在需要用户界面的任何位置使用。

`CRectTracker` 边框可以为实线或虚线。 可以为该项目指定一个阴影线，或使用阴影模式重叠来指示该项的不同状态。 可以在项的外部或内部边框上放置8个调整大小控点。  (有关调整大小控点的说明，请参阅 [GetHandleMask](#gethandlemask)。 ) 最后，可以在 `CRectTracker` 调整大小时更改项的方向。

若要使用 `CRectTracker` ，请构造 `CRectTracker` 对象并指定要初始化的显示状态。 然后，可以使用此接口向用户提供与对象关联的 OLE 项的当前状态的视觉反馈 `CRectTracker` 。

有关使用的详细信息 `CRectTracker` ，请参阅文章 [跟踪](../../mfc/trackers.md)器。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CRectTracker`

## <a name="requirements"></a>要求

**标头：** afxext。h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a> CRectTracker：： AdjustRect

当使用大小调整句柄调整跟踪矩形的大小时，由框架调用。

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>parameters

*nHandle*<br/>
使用的句柄的索引。

*lpRect*<br/>
指向矩形当前大小的指针。  (矩形的大小由其高度和宽度指定。 ) 

### <a name="remarks"></a>备注

此函数的默认行为使矩形的方向仅在 `Track` `TrackRubberBand` 允许使用反转进行调用时更改。

重写此函数可控制在拖动操作期间调整跟踪矩形。 一种方法是在返回之前调整 *lpRect* 指定的坐标。

不直接支持的特殊功能（ `CRectTracker` 例如，对齐网格或保持纵横比）可以通过重写此函数来实现。

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a> CRectTracker：： CRectTracker

创建并初始化一个 `CRectTracker` 对象。

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>parameters

*lpSrcRect*<br/>
矩形对象的坐标。

*nStyle*<br/>
指定对象的样式 `CRectTracker` 。 支持以下样式：

- `CRectTracker::solidLine` 使用实线作为矩形边框。

- `CRectTracker::dottedLine` 用点线表示矩形边框。

- `CRectTracker::hatchedBorder` 使用矩形边框的阴影模式。

- `CRectTracker::resizeInside` 位于矩形内的调整大小控点。

- `CRectTracker::resizeOutside` 尺寸控点位于矩形外部。

- `CRectTracker::hatchInside` 阴影模式包含整个矩形。

### <a name="remarks"></a>备注

默认构造函数将对象初始化为 `CRectTracker` *lpSrcRect* 中的值，并将其他大小初始化为系统默认值。 如果创建的对象没有参数，则 `m_rect` 和 `m_nStyle` 数据成员未初始化。

## <a name="crecttrackerdraw"></a><a name="draw"></a> CRectTracker：:D raw

调用此函数可绘制矩形的外线条和内部区域。

```cpp
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>parameters

*pDC*<br/>
一个指针，指向要在其上进行绘制的设备上下文。

### <a name="remarks"></a>备注

跟踪器的样式确定绘图的完成方式。 有关可用样式的详细信息，请参阅构造函数 `CRectTracker` 。

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a> CRectTracker：:D rawTrackerRect

每当跟踪器的位置在 `Track` 或成员函数内发生更改时，由框架调用 `TrackRubberBand` 。

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>parameters

*lpRect*<br/>
指向 `RECT` 包含要绘制的矩形的的指针。

*pWndClipTo*<br/>
指向用于剪辑矩形的窗口的指针。

*pDC*<br/>
一个指针，指向要在其上进行绘制的设备上下文。

*pWnd*<br/>
指向将在其上进行绘制的窗口的指针。

### <a name="remarks"></a>备注

默认实现对进行调用 `CDC::DrawFocusRect` ，后者绘制虚线矩形。

重写此函数以在跟踪操作期间提供不同的反馈。

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a> CRectTracker：： GetHandleMask

框架调用此成员函数来检索矩形大小调整控点的掩码。

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>返回值

`CRectTracker`项的大小调整句柄的掩码。

### <a name="remarks"></a>备注

调整大小控点显示在矩形的边和角上，并允许用户控制矩形的形状和大小。

矩形具有8个编号为0-7 的大小调整句柄。 每个调整大小控点都由掩码中的一个位表示;该位的值为 2 ^ *n*，其中 *n* 为大小调整句柄号。 Bits 0-3 对应于角的调整大小控点，从左上方开始顺时针移动。 Bits 4-7 对应于从最大顺时针方向开始的侧尺寸控点。 下图显示了一个矩形的大小调整控点及其相应的大小调整句柄编号和值：

![调整句柄数](../../mfc/reference/media/vc35dp1.gif "大小调整控点的数量")

的默认实现将 `GetHandleMask` 返回位的掩码，以便显示调整大小控点。 如果单一位为 on，则将绘制相应的大小调整句柄。

重写此成员函数以隐藏或显示指示的大小调整句柄。

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a> CRectTracker：： GetTrueRect

调用此函数可检索矩形的坐标。

```cpp
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>parameters

*lpTrueRect*<br/>
指向 `RECT` 结构的指针，该结构将包含对象的设备坐标 `CRectTracker` 。

### <a name="remarks"></a>备注

矩形的尺寸包括位于外边框的任何大小调整控点的高度和宽度。 返回时， *lpTrueRect* 始终是设备坐标中的规范化矩形。

## <a name="crecttrackerhittest"></a><a name="hittest"></a> CRectTracker：： System.windows.media.visualtreehelper.hittest

调用此函数可确定用户是否已获取大小调整句柄。

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>parameters

*情况*<br/>
要测试的点，以设备坐标表示。

### <a name="return-value"></a>返回值

返回的值基于枚举类型 `CRectTracker::TrackerHit` ，可以具有以下值之一：

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight` 2

- `CRectTracker::hitBottomRight` pps-2

- `CRectTracker::hitBottomLeft` 三维空间

- `CRectTracker::hitTop` 4

- `CRectTracker::hitRight` 5

- `CRectTracker::hitBottom` 共

- `CRectTracker::hitLeft` 全天候

- `CRectTracker::hitMiddle` 8

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a> CRectTracker：： m_nHandleSize

大小调整手柄的大小（以像素为单位） `CRectTracker` 。

```
int m_nHandleSize;
```

### <a name="remarks"></a>备注

用默认系统值初始化。

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a> CRectTracker：： m_rect

矩形的当前位置 (像素) 的工作区坐标。

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a> CRectTracker：： m_sizeMin

矩形的最小大小。

```
CSize m_sizeMin;
```

### <a name="remarks"></a>备注

默认值和都 `cx` `cy` 是从边框宽度的默认系统值计算而来的。 此数据成员仅由 `AdjustRect` 成员函数使用。

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a> CRectTracker：： m_nStyle

矩形的当前样式。

```
UINT m_nStyle;
```

### <a name="remarks"></a>备注

有关可能样式的列表，请参阅 [CRectTracker：： CRectTracker](#crecttracker) 。

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a> CRectTracker：： NormalizeHit

调用此函数可转换可能反转的句柄。

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>parameters

*nHandle*<br/>
用户选择的句柄。

### <a name="return-value"></a>返回值

规范化句柄的索引。

### <a name="remarks"></a>备注

如果 `CRectTracker::Track` `CRectTracker::TrackRubberBand` 使用 "允许反转" 调用或，则可以在 x 轴、y 轴或两者上反转矩形。 发生这种情况时， `HitTest` 将返回与该矩形相对应反转的句柄。 这不适用于绘制游标反馈，因为反馈取决于矩形的屏幕位置，而不是要修改的矩形数据结构部分。

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a> CRectTracker：： OnChangedRect

每当在调用期间更改跟踪器矩形时，由框架调用 `Track` 。

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>parameters

*rectOld*<br/>
包含对象的旧的设备坐标 `CRectTracker` 。

### <a name="remarks"></a>备注

调用此函数时，将删除用绘制的所有反馈 `DrawTrackerRect` 。 此函数的默认实现不执行任何操作。

如果要在调整矩形大小后执行任何操作，请重写此函数。

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a> CRectTracker：： SetCursor

调用此函数可在指针位于对象的区域时更改光标形状 `CRectTracker` 。

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>parameters

*pWnd*<br/>
指向当前包含光标的窗口。

*nHitTest*<br/>
上一个命中测试的结果，来自 WM_SETCURSOR 消息。

### <a name="return-value"></a>返回值

如果上一个命中超过跟踪器矩形，则为非零值;否则为0。

### <a name="remarks"></a>备注

从处理 WM_SETCURSOR 消息的窗口的函数内部调用此函数 (通常 `OnSetCursor`) 。

## <a name="crecttrackertrack"></a><a name="track"></a> CRectTracker：： Track

调用此函数可显示用于调整矩形大小的用户界面。

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>parameters

*pWnd*<br/>
包含矩形的窗口对象。

*情况*<br/>
相对于工作区的当前鼠标位置的设备坐标。

*bAllowInvert*<br/>
如果为 TRUE，则可以沿 x 轴或 y 轴反转矩形;否则为 FALSE。

*pWndClipTo*<br/>
绘制操作将被剪裁到的窗口。 如果为 NULL，则将 *pWnd* 用作剪辑矩形。

### <a name="return-value"></a>返回值

如果按下了 ESC 键，则将停止跟踪过程，不会更改存储在跟踪器中的矩形，并返回0。 如果更改已提交，通过移动鼠标并释放鼠标左键，新位置和/或大小将记录在跟踪器的矩形中，并返回非零值。

### <a name="remarks"></a>备注

通常从处理消息的应用程序的函数内部调用， `WM_LBUTTONDOWN` (通常 `OnLButtonDown`) 。

此函数将捕获鼠标，直到用户释放鼠标左键、按下 ESC 键或按下鼠标右键。 当用户移动鼠标光标时，将通过调用和更新反馈 `DrawTrackerRect` `OnChangedRect` 。

如果 *bAllowInvert* 为 TRUE，则可以在 x 轴或 y 轴上反转跟踪矩形。

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a> CRectTracker：： TrackRubberBand

调用此函数可选择 "带"。

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>parameters

*pWnd*<br/>
包含矩形的窗口对象。

*情况*<br/>
相对于工作区的当前鼠标位置的设备坐标。

*bAllowInvert*<br/>
如果为 TRUE，则可以沿 x 轴或 y 轴反转矩形;否则为 FALSE。

### <a name="return-value"></a>返回值

如果鼠标已移动并且矩形不为空，则为非零值;否则为0。

### <a name="remarks"></a>备注

通常在处理 WM_LBUTTONDOWN 消息的应用程序的函数中调用该消息， (通常是 `OnLButtonDown`) 的。

此函数将捕获鼠标，直到用户释放鼠标左键、按下 ESC 键或按下鼠标右键。 当用户移动鼠标光标时，将通过调用和更新反馈 `DrawTrackerRect` `OnChangedRect` 。

跟踪是使用来自右下方控点的橡皮带类型选择执行的。 如果允许使用反转，则可以通过向左或向下拖动，并向右拖动来调整矩形的大小。

## <a name="see-also"></a>请参阅

[MFC 示例跟踪器](../../overview/visual-cpp-samples.md)<br/>
[MFC 示例 DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[COleResizeBar 类](../../mfc/reference/coleresizebar-class.md)<br/>
[CRect 类](../../atl-mfc-shared/reference/crect-class.md)
