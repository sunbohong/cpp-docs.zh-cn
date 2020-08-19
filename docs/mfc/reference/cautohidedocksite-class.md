---
title: CAutoHideDockSite 类
ms.date: 11/04/2016
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
ms.openlocfilehash: 2779e643b15179b0017535fbfbb144f94e1aedbe
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562007"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite 类

`CAutoHideDockSite`扩展[CDockSite 类](../../mfc/reference/cdocksite-class.md)以实现自动隐藏停靠窗格。

## <a name="syntax"></a>语法

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|||
|-|-|
|“属性”|说明|
|`CAutoHideDockSite::CAutoHideDockSite`|构造 `CAutoHideDockSite` 对象。|
|`CAutoHideDockSite::~CAutoHideDockSite`|析构函数。|

### <a name="public-methods"></a>公共方法

|||
|-|-|
|“属性”|说明|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|指示是否在 `CAutoHideDockSite` 窗格菜单上显示。|
|[CAutoHideDockSite：： CanAcceptPane](#canacceptpane)|确定基窗格对象是否派生自 [CMFCAutoHideBar 类](../../mfc/reference/cmfcautohidebar-class.md)。|
|[CAutoHideDockSite：:D ockPane](#dockpane)|将一个窗格停靠到此 `CAuotHideDockSite` 对象。|
|[CAutoHideDockSite：： GetAlignRect](#getalignrect)|检索停靠站点的大小（以屏幕坐标表示）。|
|[CAutoHideDockSite：： RepositionPanes](#repositionpanes)|`CAutoHideDockSite`用全局边距和按钮间距重绘上的窗格。|
|[CAutoHideDockSite：： SetOffsetLeft](#setoffsetleft)|设置停靠栏左侧的边距。|
|[CAutoHideDockSite：： SetOffsetRight](#setoffsetright)|设置停靠栏右侧的边距。|
|[CAutoHideDockSite：： UnSetAutoHideMode](#unsetautohidemode)|为中的对象调用 [CMFCAutoHideBar：： UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) `CAutoHideDockSite` 。|

### <a name="data-members"></a>数据成员

|||
|-|-|
|名称|说明|
|[CAutoHideDockSite：： m_nExtraSpace](#m_nextraspace)|定义工具栏和停靠栏边缘之间的空间大小。 此空间是从左边缘或上边缘测量的，具体取决于停靠空间的对齐方式。|

## <a name="remarks"></a>备注

调用 [CFrameWndEx：： EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)时，框架会自动创建 `CAutoHideDockSite` 对象。 在大多数情况下，您不必直接实例化或使用此类。

停靠栏是停靠窗格左侧与 [CMFCAutoHideButton 类](../../mfc/reference/cmfcautohidebutton-class.md)左侧之间的差距。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>示例

下面的示例演示如何 `CAutoHideDockSite` 从对象中检索对象 `CMFCAutoHideBar` ，以及如何设置停靠栏的左边距和右边距。

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>要求

**标头：** afxautohidedocksite

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a> CAutoHideDockSite：： CanAcceptPane

确定基窗格是 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 对象还是派生自 `CMFCAutoHideBar` 。

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>参数

*pBar*\
中框架测试的基本窗格。

### <a name="return-value"></a>返回值

如果 *pBar* 是从派生的，则为 TRUE `CMFCAutoHideBar` ;否则为 FALSE。

### <a name="remarks"></a>备注

如果基窗格对象是从派生的 `CMFCAutoHideBar` ，则它可以包含 `CAutoHideDockSite` 。

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a> CAutoHideDockSite：:D ockPane

将一个窗格停靠到此 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) 对象。

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>参数

*pWnd*\
中框架停靠的窗格。

*dockMethod*\
中窗格的停靠选项。

*lpRect*\
中指定停靠窗格边界的矩形。

### <a name="remarks"></a>备注

默认实现不使用提供的参数 *dockMethod*供将来使用。

如果 *lpRect* 为 NULL，框架会将窗格置于停靠站点的默认位置。 如果停靠站点是水平的，则默认位置位于停靠站点的最左侧。 否则，默认位置位于停靠站点的顶部。

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a> CAutoHideDockSite：： GetAlignRect

检索停靠站点的大小（以屏幕坐标表示）。

```cpp
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>参数

*rect*\
中对矩形的引用。 方法在此矩形中存储停靠站点的大小。

### <a name="remarks"></a>备注

为偏移边距调整矩形，使其不包括在内。

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a> CAutoHideDockSite：： m_nExtraSpace

[CAutoHideDockSite 类](../../mfc/reference/cautohidedocksite-class.md)和[CMFCAutoHideBar 类](../../mfc/reference/cmfcautohidebar-class.md)对象的边缘之间的空间大小。

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>备注

当 `CMFCAutoHideBar` 停靠在上时 `CAutoHideDockSite` ，它不应占用整个停靠站点。 此全局变量控制的左边缘或上边框与相应边缘之间的额外空间 `CMFCAutoHideBar` `CAutoHideDockSite` 。 是否使用上边缘或左边缘取决于当前对齐方式。

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a> CAutoHideDockSite：： SetOffsetLeft

设置停靠栏左侧的边距。

```cpp
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>参数

*nOffset*<br/>
中新偏移量。

### <a name="remarks"></a>备注

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 对象以静态方式定位在 `CAutoHideDockSite` 对象上。 这意味着用户不能手动更改对象的位置 `CMFCAutoHideBar` 。 方法控制左侧和左侧的左侧 `SetOffsetLeft` 之间的间距 `CMFCAutoHideBar` ，并控制 `CAutoHideDockSite` 。

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a> CAutoHideDockSite：： SetOffsetRight

设置停靠栏右侧的边距。

```cpp
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>参数

*nOffset*<br/>
中新偏移量。

### <a name="remarks"></a>备注

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 对象以静态方式定位在 `CAutoHideDockSite` 对象上。 这意味着用户不能手动更改对象的位置 `CMFCAutoHideBar` 。 方法控制右端和右侧的右端 `SetOffsetRight` 之间的间距 `CMFCAutoHideBar` `CAutoHideDockSite` 。

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a> CAutoHideDockSite：： RepositionPanes

重绘 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)上的窗格。

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>参数

*rectNewClientArea*\
中保留值。

### <a name="remarks"></a>备注

默认实现不使用 *rectNewClientArea*。 它将用全局工具栏边距和按钮间距重绘窗格。

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a> CAutoHideDockSite：： UnSetAutoHideMode

为停靠站点上的对象调用 [CMFCAutoHideBar：： UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) 。

```cpp
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>参数

*pAutoHideToolbar*\
中指向位于的 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 对象窗格的指针 `CAutoHideDockSite` 。

### <a name="remarks"></a>备注

此方法搜索包含 *pAutoHideToolbar*的行。 它调用 `CMFCAutoHideBar.UnSetAutoHideMode` `CMFCAutoHideBar` 该行上的所有对象。 如果找不到 *pAutoHideToolbar* 或它为 NULL，此方法将调用 `CMFCAutoHideBar.UnSetAutoHideMode` 上的所有 `CMFCAutoHideBar` 对象 `CAutoHideDockSite` 。

## <a name="see-also"></a>另请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite 类](../../mfc/reference/cdocksite-class.md)
