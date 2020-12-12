---
description: 了解详细信息： COleResizeBar 类
title: COleResizeBar 类
ms.date: 11/04/2016
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
ms.openlocfilehash: bdd97e854257e2f858b52ed45f4066b26c71394d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226709"
---
# <a name="coleresizebar-class"></a>COleResizeBar 类

支持调整现有 OLE 项的控件条类型。

## <a name="syntax"></a>语法

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[COleResizeBar：： COleResizeBar](#coleresizebar)|构造 `COleResizeBar` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[COleResizeBar：： Create](#create)|创建并初始化一个 Windows 子窗口，并将其与该对象相关联 `COleResizeBar` 。|

## <a name="remarks"></a>备注

`COleResizeBar` 对象显示为带有阴影边框和外部调整控点的 [CRectTracker](../../mfc/reference/crecttracker-class.md) 。

`COleResizeBar` 对象通常是从 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) 类派生的框架窗口对象的嵌入成员。

有关详细信息，请参阅文章 [激活](../../mfc/activation-cpp.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>要求

**标头：** afxole

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a> COleResizeBar：： COleResizeBar

构造 `COleResizeBar` 对象。

```
COleResizeBar();
```

### <a name="remarks"></a>备注

调用 `Create` 以创建大小调整条形对象。

## <a name="coleresizebarcreate"></a><a name="create"></a> COleResizeBar：： Create

创建一个子窗口，并将其与 `COleResizeBar` 对象关联。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>parameters

*pParentWnd*<br/>
指向调整大小栏的父窗口的指针。

*dwStyle*<br/>
指定 [窗口样式](../../mfc/reference/styles-used-by-mfc.md#window-styles) 特性。

*nID*<br/>
调整大小栏的子窗口 ID。

### <a name="return-value"></a>返回值

如果创建了调整大小条，则为非零值;否则为0。

## <a name="see-also"></a>请参阅

[MFC 示例 SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 类](../../mfc/reference/ccontrolbar-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc 类](../../mfc/reference/coleserverdoc-class.md)
