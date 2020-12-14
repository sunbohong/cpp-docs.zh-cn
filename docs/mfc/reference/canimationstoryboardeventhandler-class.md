---
description: 了解详细信息： CAnimationStoryboardEventHandler 类
title: CAnimationStoryboardEventHandler 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
ms.openlocfilehash: 7208ba91ec78a6de688699183b55a691b8e3d28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254737"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler 类

实现回调，它在演示图板状态更改时或演示图板更新时由动画 API 调用。

## <a name="syntax"></a>语法

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationStoryboardEventHandler：： CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|构造 `CAnimationStoryboardEventHandler` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationStoryboardEventHandler：： CreateInstance](#createinstance)|创建回调的实例 `CAnimationStoryboardEventHandler` 。|
|[CAnimationStoryboardEventHandler：： OnStoryboardStatusChanged](#onstoryboardstatuschanged)|处理 `OnStoryboardStatusChanged` 事件，在情节提要的状态更改 (重写时发生 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged` 。 ) |
|[CAnimationStoryboardEventHandler：： OnStoryboardUpdated](#onstoryboardupdated)|处理 `OnStoryboardUpdated` 事件，该事件在情节提要更新 (重写时发生 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated` 。 ) |
|[CAnimationStoryboardEventHandler：： SetAnimationController](#setanimationcontroller)|存储指向用于路由事件的动画控制器的指针。|

## <a name="remarks"></a>备注

当你调用时，将创建此事件处理程序并将其传递给 `IUIAnimationStoryboard::SetStoryboardEventHandler` 方法 `CAnimationController::EnableStoryboardEventHandler` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a> CAnimationStoryboardEventHandler：： CAnimationStoryboardEventHandler

构造 CAnimationStoryboardEventHandler 对象。

```
CAnimationStoryboardEventHandler();
```

## <a name="canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationStoryboardEventHandler：： CreateInstance

创建 CAnimationStoryboardEventHandler 回调的实例。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>parameters

*pAnimationController*<br/>
指向将接收事件的动画控制器的指针。

*ppHandler*

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a> CAnimationStoryboardEventHandler：： OnStoryboardStatusChanged

处理 OnStoryboardStatusChanged 事件，这些事件在情节提要的状态更改时发生

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>parameters

*情节提要*<br/>
指向其状态已更改的情节提要的指针。

*newStatus*<br/>
指定新的情节提要状态。

*previousStatus*<br/>
指定上一个情节提要状态。

### <a name="return-value"></a>返回值

如果该方法成功，则 S_OK;否则 E_FAIL。

## <a name="canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a> CAnimationStoryboardEventHandler：： OnStoryboardUpdated

处理 OnStoryboardUpdated 事件，这些事件在情节提要更新时发生

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>parameters

*情节提要*<br/>
已更新的情节提要的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则 S_OK;否则 E_FAIL。

## <a name="canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationStoryboardEventHandler：： SetAnimationController

存储指向用于路由事件的动画控制器的指针。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>parameters

*pAnimationController*<br/>
指向将接收事件的动画控制器的指针。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
