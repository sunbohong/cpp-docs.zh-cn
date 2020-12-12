---
description: 了解详细信息： InvokeHelper 结构
title: InvokeHelper 结构
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 0b9bb8abb59cce5a3c25d795d0946ffbe88d0076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299015"
---
# <a name="invokehelper-structure"></a>InvokeHelper 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>parameters

*TDelegateInterface*<br/>
委托接口类型。

*TCallback*<br/>
事件处理程序函数的类型。

*argCount*<br/>
专用化中参数的数目 `InvokeHelper` 。

## <a name="remarks"></a>备注

`Invoke()`基于指定的参数数量和类型提供方法的实现。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称     | 描述
-------- | -----------------------------------------------------------------------------
`Traits` | 定义每个事件处理程序参数的类型的类的同义词。

### <a name="public-constructors"></a>公共构造函数

“属性”                                        | 描述
------------------------------------------- | -------------------------------------------------------
[InvokeHelper：： InvokeHelper](#invokehelper) | 初始化 `InvokeHelper` 类的新实例。

### <a name="public-methods"></a>公共方法

“属性”                            | 描述
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper：： Invoke](#invoke) | 调用其签名包含指定数量的自变量的事件处理程序。

### <a name="public-data-members"></a>公共数据成员

名称                                 | 描述
------------------------------------ | ----------------------------------------------------------
[InvokeHelper：： callback_](#callback) | 表示事件发生时要调用的事件处理程序。

## <a name="inheritance-hierarchy"></a>继承层次结构

`InvokeHelper`

## <a name="requirements"></a>要求

**标头：** 事件。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="invokehelpercallback_"></a><a name="callback"></a> InvokeHelper：： callback_

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
TCallback callback_;
```

### <a name="remarks"></a>备注

表示事件发生时要调用的事件处理程序。

`TCallback`模板参数指定事件处理程序的类型。

## <a name="invokehelperinvoke"></a><a name="invoke"></a> InvokeHelper：： Invoke

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>parameters

*arg1*<br/>
参数1。

*arg2*<br/>
参数2。

*arg3*<br/>
参数3。

*arg4*<br/>
参数4。

*arg5*<br/>
参数5。

*arg6*<br/>
参数6。

*arg7*<br/>
参数7。

*arg8*<br/>
参数8。

*arg9*<br/>
参数9。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为说明错误的 HRESULT。

### <a name="remarks"></a>备注

调用其签名包含指定数量的自变量的事件处理程序。

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a> InvokeHelper：： InvokeHelper

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>parameters

*拨*<br/>
事件处理程序。

### <a name="remarks"></a>备注

初始化 `InvokeHelper` 类的新实例。

`TCallback`模板参数指定事件处理程序的类型。
