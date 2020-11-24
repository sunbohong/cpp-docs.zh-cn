---
title: __hook
description: 了解如何使用 Microsoft c + + extension 关键字 `__hook` 进行本机事件处理。
ms.date: 11/20/2020
f1_keywords:
- __hook_cpp
- __hook
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.openlocfilehash: 2a2bde221c53f0e1d420e2ab3a88eb299f6c284c
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483251"
---
# <a name="__hook-keyword"></a>`__hook` 关键字

将处理程序方法与事件关联。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>语法

```cpp
long __hook(
    &SourceClass::EventMethod,
    source,
    &ReceiverClass::HandlerMethod
    [, receiver = this]
);

long __hook(
    interface,
    source
);
```

### <a name="parameters"></a>参数

*`&SourceClass::EventMethod`*\
指向要将事件处理程序方法挂钩到的事件方法的指针：

- 本机 c + + 事件： *`SourceClass`* 是事件源类， *`EventMethod`* 是事件。

- COM 事件： *`SourceClass`* 是事件源接口， *`EventMethod`* 是其方法之一。

- 托管事件： *`SourceClass`* 是事件源类， *`EventMethod`* 是事件。

*`interface`*\
要挂钩到的接口名称 *`receiver`* ，仅适用于其属性的参数为的 COM 事件接收器 *`layout_dependent`* [`event_receiver`](../windows/attributes/event-receiver.md) **`true`** 。

*`source`*\
指向事件源的实例的指针。 根据 `type` 中指定的代码 `event_receiver` ， *`source`* 可以是以下类型之一：

- 本机事件源对象指针。

- `IUnknown` (COM 源) 的基于的指针。

- 托管对象指针（针对托管事件）。

*`&ReceiverClass::HandlerMethod`*\
指向要挂钩到事件的事件处理程序方法的指针。 处理程序被指定为类的方法或对相同的引用。 如果未指定类名，则 **`__hook`** 假定该类是从其调用的类。

- 本机 c + + 事件： *`ReceiverClass`* 是事件接收器类， `HandlerMethod` 是处理程序。

- COM 事件： *`ReceiverClass`* 是事件接收器接口， *`HandlerMethod`* 是它的一个处理程序。

- 托管事件： *`ReceiverClass`* 是事件接收器类， *`HandlerMethod`* 是处理程序。

*`receiver`*\
 (可选) 指向事件接收器类的实例的指针。 如果未指定接收方，则默认值是调用的接收方类或结构 **`__hook`** 。

## <a name="usage"></a>使用情况

可以在事件接收器类的外部的任何函数范围（包括 main）中使用。

## <a name="remarks"></a>注解

使用事件接收器中的内部函数将 **`__hook`** 处理程序方法与事件方法关联或挂钩。 随后会在源引发指定事件时调用指定的事件处理程序。 可以将多个处理程序挂钩到单个事件，或将多个事件挂钩到单个处理程序。

有两种形式的 **`__hook`** 。 在大多数情况下，你可以在大多数情况下使用第一个 (四参数) 窗体，具体而言，对于 COM 事件接收，其中属性的 *layout_dependent* 参数 [`event_receiver`](../windows/attributes/event-receiver.md) 为 **`false`** 。

在这些情况下，在其中一个方法上触发事件之前，不需要在接口中挂接所有方法。 只需要挂钩处理事件的方法。 只能 **`__hook`** 对的 COM 事件接收器使用第二个 (参数) 形式 *`layout_dependent`* **`= true`** 。

**`__hook`** 返回一个长整型值。 非零返回值表示发生了错误（托管事件引发了异常）。

编译器将检查是否存在事件以及事件签名是否与委托签名一致。

**`__hook`** **`__unhook`** 除了 COM 事件之外，还可以在事件接收器之外调用和。

使用的替代方法 **`__hook`** 是使用 + = 运算符。

有关新语法中的托管事件编码的信息，请参阅 [`event`](../extensions/event-cpp-component-extensions.md) 。

> [!NOTE]
> 模板类或结构不能包含事件。

## <a name="example"></a>示例

有关示例，请参阅 [本机 c + + 中的事件处理](../cpp/event-handling-in-native-cpp.md) 和 [COM 中的事件处理](../cpp/event-handling-in-com.md) 。

## <a name="see-also"></a>另请参阅

[字](../cpp/keywords-cpp.md)\
[事件处理](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
