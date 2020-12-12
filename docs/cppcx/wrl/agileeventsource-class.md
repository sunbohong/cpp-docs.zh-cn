---
description: 了解详细信息： AgileEventSource 类
title: AgileEventSource 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
helpviewer_keywords:
- AgileEventSource class
ms.openlocfilehash: d2e48d59d8706eb65828bc5b77ffaf9d4158bc1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204571"
---
# <a name="agileeventsource-class"></a>AgileEventSource 类

表示由 agile 组件引发的事件，该组件是可从任何线程访问的组件。 继承自 [EventSource](eventsource-class.md) ，并 `Add` 使用附加类型参数重写成员函数，以便为如何调用 agile 事件指定选项。

## <a name="syntax"></a>语法

```cpp
template<
    typename TDelegateInterface,
    typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>
>
class AgileEventSource :
    public Microsoft::WRL::EventSource<
        TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>parameters

*TDelegateInterface*<br/>
表示事件处理程序的委托的接口。

*TEventSourceOptions*<br/>
[InvokeModeOptions](invokemodeoptions-structure.md)结构，其 invokeMode 字段设置为 `InvokeMode::StopOnFirstError` 或 `InvokeMode::FireAll` 。

## <a name="remarks"></a>备注

Windows 运行时中的绝大部分组件都是 agile 组件。 有关详细信息，请参阅 [线程处理和封送处理 (c + +/cx) ](../../cppcx/threading-and-marshaling-c-cx.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`EventSource`

`AgileEventSource`

## <a name="requirements"></a>要求

**标头：** 事件。h

**命名空间：** Microsoft::WRL

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[AgileEventSource：： Add 方法](#add)|将指定委托接口表示的敏捷事件处理程序追加到当前 **AgileEventSource** 对象的事件处理程序集。|

## <a name="agileeventsourceadd-method"></a><a name="add"></a> AgileEventSource：： Add 方法

将指定委托接口表示的事件处理程序追加到当前 [EventSource](eventsource-class.md) 对象的事件处理程序集。

### <a name="syntax"></a>语法

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>parameters

*delegateInterface*<br/>
委托对象的接口，它表示事件处理程序。

*token*<br/>
此操作完成后，表示事件的句柄。 使用此标记作为方法的参数来 `Remove()` 放弃事件处理程序。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
