---
description: 了解详细信息： CMFCBaseToolBar 类
title: CMFCBaseToolBar 类
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar::GetDockingMode
- AFXBASETOOLBAR/CMFCBaseToolBar::GetMinSize
- AFXBASETOOLBAR/CMFCBaseToolBar::OnAfterChangeParent
helpviewer_keywords:
- CMFCBaseToolBar [MFC], GetDockingMode
- CMFCBaseToolBar [MFC], GetMinSize
- CMFCBaseToolBar [MFC], OnAfterChangeParent
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
ms.openlocfilehash: 37597e4cb300e0d6d16c92f105e332c18c5beda7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247912"
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar 类

工具栏的基类。

## <a name="syntax"></a>语法

```
class CMFCBaseToolBar : public CPane
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCBaseToolBar::CMFCBaseToolBar`|默认构造函数。|
|`CMFCBaseToolBar::~CMFCBaseToolBar`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|`CMFCBaseToolBar::CreateObject`|由框架用于创建此类类型的动态实例。|
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|返回停靠模式。  (重写 [CBasePane：： GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)。 ) |
|[CMFCBaseToolBar::GetMinSize](#getminsize)|返回工具栏的最小大小。  (重写 [CPane：： GetMinSize](../../mfc/reference/cpane-class.md#getminsize)。 ) |
|[CMFCBaseToolBar::OnAfterChangeParent](#onafterchangeparent)|在窗格的父项更改后由框架调用。  (重写 [CBasePane：： OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent)。 ) |

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxbasetoolbar

## <a name="cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a> CMFCBaseToolBar::GetDockingMode

返回停靠模式。

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>返回值

停靠模式。

## <a name="cmfcbasetoolbargetminsize"></a><a name="getminsize"></a> CMFCBaseToolBar::GetMinSize

返回工具栏的最小大小。

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>parameters

*大小*<br/>
弄工具栏的最小大小。

## <a name="cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a> CMFCBaseToolBar::OnAfterChangeParent

在窗格的父项更改后由框架调用。

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>parameters

*pWndOldParent*<br/>
中指向上一个父窗口的指针。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)
