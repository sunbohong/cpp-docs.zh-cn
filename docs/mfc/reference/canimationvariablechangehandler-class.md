---
description: 了解详细信息： CAnimationVariableChangeHandler 类
title: CAnimationVariableChangeHandler 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 1c97bc908a29bfb7edf2222f6df117fefdaf4091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207873"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler 类

实现回调，它在动画变量值更改时由动画 API 调用。

## <a name="syntax"></a>语法

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|构造 `CAnimationVariableChangeHandler` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|创建对象的实例 `CAnimationVariableChangeHandler` 。|
|[CAnimationVariableChangeHandler：： OnValueChanged](#onvaluechanged)|当动画变量的值已更改时调用。 （重写 `CUIAnimationVariableChangeHandlerBase::OnValueChanged`。）|
|[CAnimationVariableChangeHandler：： SetAnimationController](#setanimationcontroller)|存储指向用于路由事件的动画控制器的指针。|

## <a name="remarks"></a>备注

此事件处理程序在 `IUIAnimationVariable::SetVariableChangeHandler` 您调用或 (时创建并传递给方法，该事件处理程序 `CAnimationVariable::EnableValueChangedEvent` `CAnimationBaseObject::EnableValueChangedEvent` 对所有封装在动画对象) 中的动画变量启用此事件。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a> CAnimationVariableChangeHandler：： OnValueChanged

当动画变量的值已更改时调用。

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>parameters

*情节提要*<br/>
对变量进行动画处理的情节提要。

variable<br/>
已更新的动画变量。

*newValue*<br/>
新值。

*previousValue*<br/>
以前的值。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationVariableChangeHandler：： SetAnimationController

存储指向用于路由事件的动画控制器的指针。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>parameters

*pAnimationController*<br/>
指向将接收事件的动画控制器的指针。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
