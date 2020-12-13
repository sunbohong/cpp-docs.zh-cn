---
description: 了解详细信息： CAnimationTimerEventHandler 类
title: CAnimationTimerEventHandler 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: 5d5f3e07eeb7ffe3f3bb226afd566330808303ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336763"
---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler 类

实现回调，它在计时事件发生时由动画 API 调用。

## <a name="syntax"></a>语法

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationTimerEventHandler：： CreateInstance](#createinstance)|创建回调的实例 `CAnimationTimerEventHandler` 。|
|[CAnimationTimerEventHandler：： OnPostUpdate](#onpostupdate)|处理动画更新完成后发生的事件。 （重写 `CUIAnimationTimerEventHandlerBase::OnPostUpdate`。）|
|[CAnimationTimerEventHandler：： OnPreUpdate](#onpreupdate)|处理动画更新开始之前发生的事件。 （重写 `CUIAnimationTimerEventHandlerBase::OnPreUpdate`。）|
|[CAnimationTimerEventHandler：： OnRenderingTooSlow](#onrenderingtooslow)|处理当动画的呈现帧速率低于最小理想帧速率时发生的事件。 （重写 `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`。）|
|[CAnimationTimerEventHandler：： SetAnimationController](#setanimationcontroller)|存储指向用于路由事件的动画控制器的指针。|

## <a name="remarks"></a>备注

当你调用 CAnimationController：： EnableAnimationTimerEventHandler 时，将创建此事件处理程序并将其传递给 IUIAnimationTimer：： SetTimerEventHandler。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationTimerEventHandler：： CreateInstance

创建 CAnimationTimerEventHandler 回调的实例。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>parameters

*pAnimationController*<br/>
指向将接收事件的动画控制器的指针。

*ppTimerEventHandler*

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a> CAnimationTimerEventHandler：： OnPostUpdate

处理动画更新完成后发生的事件。

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>返回值

如果该方法成功，则 S_OK;否则 E_FAIL。

## <a name="canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a> CAnimationTimerEventHandler：： OnPreUpdate

处理动画更新开始之前发生的事件。

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>返回值

如果该方法成功，则 S_OK;否则 E_FAIL。

## <a name="canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a> CAnimationTimerEventHandler：： OnRenderingTooSlow

处理当动画的呈现帧速率低于最小理想帧速率时发生的事件。

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>parameters

*fps*

### <a name="return-value"></a>返回值

如果该方法成功，则 S_OK;否则 E_FAIL。

## <a name="canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationTimerEventHandler：： SetAnimationController

存储指向用于路由事件的动画控制器的指针。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>parameters

*pAnimationController*<br/>
指向将接收事件的动画控制器的指针。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
