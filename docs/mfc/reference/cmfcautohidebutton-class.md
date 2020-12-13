---
description: 了解详细信息： CMFCAutoHideButton 类
title: CMFCAutoHideButton 类
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
ms.openlocfilehash: 9d100417193ea8a757b02b9cc8fad0cdedf668f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336578"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton 类

显示或隐藏配置为隐藏的 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 按钮。

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton::Create](#create)|创建并初始化自动隐藏按钮。|
|[CMFCAutoHideButton：： GetAlignment](#getalignment)|检索自动隐藏按钮的对齐方式。|
|[CMFCAutoHideButton：： GetAutoHideWindow](#getautohidewindow)|返回与 "自动隐藏" 按钮关联的 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 对象。|
|[CMFCAutoHideButton：： GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton：： GetRect](#getrect)||
|[CMFCAutoHideButton：： GetSize](#getsize)|确定自动隐藏按钮的大小。|
|[CMFCAutoHideButton：： GetTextSize](#gettextsize)|返回自动隐藏按钮的文本标签大小。|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|突出显示自动隐藏按钮。|
|[CMFCAutoHideButton::IsActive](#isactive)|指示自动隐藏按钮是否处于活动状态。|
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|返回自动隐藏按钮的突出显示状态。|
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|确定自动隐藏按钮的方向是水平还是垂直。|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton::IsVisible](#isvisible)|指示按钮是否可见。|
|[CMFCAutoHideButton::Move](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|框架在绘制自动隐藏按钮时调用此方法。|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|框架在绘制自动隐藏按钮的边框时调用此方法。|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|框架在填充自动隐藏按钮的背景时调用此方法。|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|显示或隐藏关联的 [CDockablePane 类](../../mfc/reference/cdockablepane-class.md)。|
|[CMFCAutoHideButton::ShowButton](#showbutton)|显示或隐藏自动隐藏按钮。|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>备注

创建时， `CMFCAutoHideButton` 对象将附加到 [CDockablePane 类](../../mfc/reference/cdockablepane-class.md)。 `CDockablePane` 对象随着用户与 `CMFCAutoHideButton` 对象交互而隐藏或显示。

默认情况下，框架在用户打开“自动隐藏”时自动创建 `CMFCAutoHideButton`。 框架可创建自定义 UI 类的元素而不是 `CMFCAutoHideButton` 类。 若要指定框架应使用的自定义 UI 类，请将静态成员变量 `CMFCAutoHideBar::m_pAutoHideButtonRTS` 设置为自定义 UI 类。 默认情况下，此变量设置为 `CMFCAutoHideButton`。

## <a name="example"></a>示例

下面的示例演示如何构造 `CMFCAutoHideButton` 对象和在 `CMFCAutoHideButton` 类中使用各种方法。 该示例演示如何使用 `CMFCAutoHideButton` 对象的 `Create` 方法来初始化该对象，并显示关联的 `CDockablePane` 类和自动隐藏按钮。

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>要求

**标头：** afxautohidebutton.h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a> CMFCAutoHideButton：： BringToTop

```cpp
void BringToTop();
```

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a> CMFCAutoHideButton：： Create

创建并初始化自动隐藏按钮。

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>parameters

*pParentBar*<br/>
中指向父工具栏的指针。

*pAutoHideWnd*<br/>
中指向 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 对象的指针。 此自动隐藏按钮将隐藏并显示 `CDockablePane` 。

*dwAlignment*<br/>
中一个值，该值指定按钮与主框架窗口的对齐方式。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

创建 `CMFCAutoHideButton` 对象时，必须将 "自动隐藏" 按钮与特定的关联 `CDockablePane` 。 用户可以使用 "自动隐藏" 按钮隐藏和显示关联的 `CDockablePane` 。

*DwAlignment* 参数指示自动隐藏按钮位于应用程序中的位置。 该参数可为下列任一值：

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a> CMFCAutoHideButton：： GetAlignment

检索自动隐藏按钮的对齐方式。

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>返回值

包含自动隐藏按钮的当前对齐方式的 DWORD 值。

### <a name="remarks"></a>备注

"自动隐藏" 按钮的对齐方式指示按钮驻留在应用程序上的位置。 它可以是下列值之一：

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a> CMFCAutoHideButton：： GetAutoHideWindow

返回与 "自动隐藏" 按钮关联的 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 对象。

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>返回值

指向关联对象的指针 `CDockablePane` 。

### <a name="remarks"></a>备注

若要将自动隐藏按钮与关联 `CDockablePane` ，请将 `CDockablePane` 作为参数传递给 [CMFCAutoHideButton：： Create](#create) 方法。

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a> CMFCAutoHideButton：： GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a> CMFCAutoHideButton：： GetRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a> CMFCAutoHideButton：： GetSize

确定自动隐藏按钮的大小。

```
CSize GetSize() const;
```

### <a name="return-value"></a>返回值

一个 `CSize` 包含按钮大小的对象。

### <a name="remarks"></a>备注

计算大小包括自动隐藏按钮的边框大小。

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a> CMFCAutoHideButton：： GetTextSize

返回自动隐藏按钮的文本标签大小。

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>返回值

一个 [CSize](../../atl-mfc-shared/reference/csize-class.md) 对象，该对象包含 "自动隐藏" 按钮的文本大小。

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a> CMFCAutoHideButton：： IsActive

指示自动隐藏按钮是否处于活动状态。

```
BOOL IsActive() const;
```

### <a name="return-value"></a>返回值

如果 "自动隐藏" 按钮处于活动状态，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

显示关联的 [CDockablePane 类](../../mfc/reference/cdockablepane-class.md) 窗口时，"自动隐藏" 按钮处于活动状态。

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a> CMFCAutoHideButton：： IsHorizontal

确定自动隐藏按钮的方向是水平还是垂直。

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>返回值

如果按钮是水平的，则为非零值;否则为0。

### <a name="remarks"></a>备注

创建 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) 对象时，框架设置该对象的方向。  可以通过使用 [CMFCAutoHideButton：： Create](#create)方法中的 *dwAlignment* 参数来控制方向。

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a> CMFCAutoHideButton：： IsTop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a> CMFCAutoHideButton：： IsVisible

指示 "自动隐藏" 按钮是否可见。

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>返回值

如果按钮可见，则为 TRUE;否则为 FALSE。

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a> CMFCAutoHideButton：： OnDraw

框架在绘制自动隐藏按钮时调用此方法。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

### <a name="remarks"></a>备注

如果要在应用程序中自定义自动隐藏按钮的外观，请创建一个派生自的新类 `CMFCAutoHideButton` 。 在派生类中，重写此方法。

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a> CMFCAutoHideButton：： OnDrawBorder

框架在绘制自动隐藏按钮的边框时调用此方法。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*rectBounds*<br/>
中自动隐藏按钮的边框。

*rectBorderSize*<br/>
中"自动隐藏" 按钮两侧的边框宽度。

### <a name="remarks"></a>备注

如果要自定义应用程序中每个自动隐藏按钮的边框，请创建一个派生自的新类 `CMFCAutoHideButton` 。 在派生类中，重写此方法。

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a> CMFCAutoHideButton：： OnFillBackground

框架在填充自动隐藏按钮的背景时调用此方法。

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*rect*<br/>
中自动隐藏按钮的边框。

### <a name="remarks"></a>备注

如果要在应用程序中自定义自动隐藏按钮的背景，请创建一个派生自的新类 `CMFCAutoHideButton` 。 在派生类中，重写此方法。

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a> CMFCAutoHideButton：： ShowAttachedWindow

显示或隐藏关联的 [CDockablePane 类](../../mfc/reference/cdockablepane-class.md)。

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>parameters

*bShow*<br/>
中一个布尔值，指定此方法是否显示附加的 `CDockablePane` 。

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a> CMFCAutoHideButton：： ShowButton

显示或隐藏自动隐藏按钮。

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>parameters

*bShow*<br/>
中一个布尔值，指定是否显示 "自动隐藏" 按钮。

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a> CMFCAutoHideButton：： Move

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>parameters

中 *nOffset*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a> CMFCAutoHideButton：： ReplacePane

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>parameters

中 *pNewBar*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a> CMFCAutoHideButton：： UnSetAutoHideMode

禁用自动隐藏模式。

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>parameters

*pFirstBarInGroup*<br/>
中指向组中第一个条形的指针。

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a> CMFCAutoHideButton：： HighlightButton

突出显示 "自动隐藏" 按钮。

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>parameters

*bHighlight*<br/>
指定新的 "自动隐藏" 按钮状态。 如果为 TRUE，则表示该按钮突出显示，FALSE 表示未突出显示该按钮。

### <a name="remarks"></a>备注

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a> CMFCAutoHideButton：： IsHighlighted

返回 "自动隐藏" 按钮的突出显示状态。

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>返回值

如果突出显示 "自动隐藏" 按钮，则返回 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar 类](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDockSite 类](../../mfc/reference/cautohidedocksite-class.md)
