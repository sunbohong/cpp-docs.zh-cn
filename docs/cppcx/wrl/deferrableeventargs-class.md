---
description: 了解详细信息： DeferrableEventArgs 类
title: DeferrableEventArgs 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 23dae7fef88ff7978790e79a0486a83815467f5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272924"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs 类

一种用于延迟事件的事件参数类型的模板类。

## <a name="syntax"></a>语法

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>parameters

*TEventArgsInterface*<br/>
声明延迟事件的自变量的接口类型。

*TEventArgsClass*<br/>
实现 *TEventArgsInterface* 的类。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

| “属性” | 描述 |
|--|--|
| [DeferrableEventArgs：： GetDeferral](#getdeferral) | 获取 [对延迟的对象的](/uwp/api/windows.foundation.deferral) 引用，该对象表示一个延迟事件。 |
| [DeferrableEventArgs：： InvokeAllFinished](#invokeallfinished) | 调用以指示处理延迟事件的全部过程都已完成。 |

## <a name="remarks"></a>备注

将此类的实例传递给延迟事件的事件句柄。 模板参数表示一个接口，该接口为特定类型的延迟事件定义事件自变量的详细信息以及定义实现该接口的类。

此类显示为一个延迟事件的事件处理程序的第一个参数。 您可以调用 [GetDeferral](#getdeferral) 方法来获取延迟对象，您可以 [从该对象](/uwp/api/windows.foundation.deferral) 获取有关延迟事件的所有信息。 处理完事件后，应对 Deferral 对象调用 Complete。 然后，应在事件处理程序方法的末尾调用 [InvokeAllFinished](#invokeallfinished) ，以确保正确地传达所有延迟事件的完成。

## <a name="requirements"></a>要求

**标头：** 事件。h

**命名空间：** Microsoft::WRL

## <a name="deferrableeventargsgetdeferral"></a><a name="getdeferral"></a> DeferrableEventArgs：： GetDeferral

获取 [对延迟的对象的](/uwp/api/windows.foundation.deferral) 引用，该对象表示一个延迟事件。

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>parameters

*result*<br/>
当调用完成时，将引用 [延迟](/uwp/api/windows.foundation.deferral) 对象的指针。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

## <a name="deferrableeventargsinvokeallfinished"></a><a name="invokeallfinished"></a> DeferrableEventArgs：： InvokeAllFinished

调用以指示处理延迟事件的全部过程都已完成。

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>备注

在事件源调用 [InvokeAll](eventsource-class.md#invokeall)后，应调用此方法。 调用此方法将阻止发生进一步的延迟，并且如果没有发生延迟将强制完成处理程序来执行。
