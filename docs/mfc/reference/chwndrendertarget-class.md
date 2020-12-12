---
description: 了解详细信息： CHwndRenderTarget 类
title: CHwndRenderTarget 类
ms.date: 11/04/2016
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
ms.openlocfilehash: 3a3058105fff5e5ac304f2cc980cd93f2bac70a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143632"
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget 类

ID2D1HwndRenderTarget 的包装器。

## <a name="syntax"></a>语法

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CHwndRenderTarget：： CHwndRenderTarget](#chwndrendertarget)|从 HWND 构造 CHwndRenderTarget 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CHwndRenderTarget：： Attach](#attach)|将现有呈现器目标接口附加到对象|
|[CHwndRenderTarget：： CheckWindowState](#checkwindowstate)|指示与此呈现器目标关联的 HWND 是否为封闭像素。|
|[CHwndRenderTarget：： Create](#create)|创建与窗口关联的呈现器目标|
|[CHwndRenderTarget：:D etach](#detach)|从对象分离呈现目标接口|
|[CHwndRenderTarget：： GetHwnd](#gethwnd)|返回与此呈现器目标关联的 HWND。|
|[CHwndRenderTarget：： GetHwndRenderTarget](#gethwndrendertarget)|返回 ID2D1HwndRenderTarget 接口。|
|[CHwndRenderTarget：：重新创建](#recreate)|重新创建与窗口关联的呈现器目标|
|[CHwndRenderTarget：： Resize](#resize)|将呈现器目标的大小更改为指定的像素大小|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CHwndRenderTarget：： operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|返回 ID2D1HwndRenderTarget 接口。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CHwndRenderTarget：： m_pHwndRenderTarget](#m_phwndrendertarget)|指向 ID2D1HwndRenderTarget 对象的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="chwndrendertargetattach"></a><a name="attach"></a> CHwndRenderTarget：： Attach

将现有呈现器目标接口附加到对象

```cpp
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>parameters

*pTarget*<br/>
现有的呈现器目标接口。 不能为 NULL

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a> CHwndRenderTarget：： CheckWindowState

指示与此呈现器目标关联的 HWND 是否为封闭像素。

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>返回值

一个值，该值指示与此呈现器目标关联的 HWND 是否为封闭像素。

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a> CHwndRenderTarget：： CHwndRenderTarget

从 HWND 构造 CHwndRenderTarget 对象。

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>parameters

*hwnd*<br/>
与此呈现器目标关联的 HWND

## <a name="chwndrendertargetcreate"></a><a name="create"></a> CHwndRenderTarget：： Create

创建与窗口关联的呈现器目标

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>parameters

*hWnd*<br/>
与此呈现器目标关联的 HWND

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE

## <a name="chwndrendertargetdetach"></a><a name="detach"></a> CHwndRenderTarget：:D etach

从对象分离呈现目标接口

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>返回值

指向分离的呈现器目标接口的指针。

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a> CHwndRenderTarget：： GetHwnd

返回与此呈现器目标关联的 HWND。

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>返回值

与此呈现器目标关联的 HWND。

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a> CHwndRenderTarget：： GetHwndRenderTarget

返回 ID2D1HwndRenderTarget 接口。

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>返回值

指向 ID2D1HwndRenderTarget 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a> CHwndRenderTarget：： m_pHwndRenderTarget

指向 ID2D1HwndRenderTarget 对象的指针。

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a> CHwndRenderTarget：： operator ID2D1HwndRenderTarget *

返回 ID2D1HwndRenderTarget 接口。

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>返回值

指向 ID2D1HwndRenderTarget 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a> CHwndRenderTarget：：重新创建

重新创建与窗口关联的呈现器目标

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>parameters

*hWnd*<br/>
与此呈现器目标关联的 HWND

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="chwndrendertargetresize"></a><a name="resize"></a> CHwndRenderTarget：： Resize

将呈现器目标的大小更改为指定的像素大小

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>parameters

*大小*<br/>
呈现器目标的新大小（以设备像素为单位）

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
