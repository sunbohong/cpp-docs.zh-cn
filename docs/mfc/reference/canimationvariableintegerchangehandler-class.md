---
description: 了解详细信息： CAnimationVariableIntegerChangeHandler 类
title: CAnimationVariableIntegerChangeHandler 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
ms.openlocfilehash: 53a0a1838e021294b4ccc870e6f01b873233a0c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336734"
---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler 类

实现回调，它在动画变量值更改时由动画 API 调用。

## <a name="syntax"></a>语法

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler：： CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|构造 `CAnimationVariableIntegerChangeHandler` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler：： CreateInstance](#createinstance)|创建回调的实例 `CAnimationVariableIntegerChangeHandler` 。|
|[CAnimationVariableIntegerChangeHandler：： OnIntegerValueChanged](#onintegervaluechanged)|当动画变量的值已更改时调用。 （重写 `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`。）|
|[CAnimationVariableIntegerChangeHandler：： SetAnimationController](#setanimationcontroller)|存储指向用于路由事件的动画控制器的指针。|

## <a name="remarks"></a>备注

当你调用 CAnimationVariable：： EnableIntegerValueChangedEvent 或 CAnimationBaseObject：： EnableIntegerValueChangedEvent 时，将创建此事件处理程序并将其传递给 IUIAnimationVariable：： SetVariableIntegerChangeHandler 方法 (，该事件处理程序将为所有封装在动画对象) 中的动画变量启用此事件。

## <a name="inheritance-hierarchy"></a>继承层次结构

[MFC 类](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationvariableintegerchangehandlercanimationvariableintegerchangehandler"></a><a name="canimationvariableintegerchangehandler"></a> CAnimationVariableIntegerChangeHandler：： CAnimationVariableIntegerChangeHandler

构造 CAnimationVariableIntegerChangeHandler 对象。

```
CAnimationVariableIntegerChangeHandler ();
```

## <a name="canimationvariableintegerchangehandlercreateinstance"></a><a name="createinstance"></a> CAnimationVariableIntegerChangeHandler：： CreateInstance

创建 CAnimationVariableIntegerChangeHandler 回调的实例。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>parameters

*pAnimationController*<br/>
指向将接收事件的动画控制器的指针。

*ppHandler*

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="canimationvariableintegerchangehandleronintegervaluechanged"></a><a name="onintegervaluechanged"></a> CAnimationVariableIntegerChangeHandler：： OnIntegerValueChanged

当动画变量的值已更改时调用。

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>parameters

*情节提要*<br/>
对变量进行动画处理的情节提要。

variable<br/>
已更新的动画变量。

*newValue*<br/>
新的舍入值。

*previousValue*<br/>
上一个舍入的值。

### <a name="return-value"></a>返回值

如果该方法成功，则 S_OK;否则 E_FAIL。

## <a name="canimationvariableintegerchangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationVariableIntegerChangeHandler：： SetAnimationController

存储指向用于路由事件的动画控制器的指针。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>parameters

*pAnimationController*<br/>
指向将接收事件的动画控制器的指针。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
