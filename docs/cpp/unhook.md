---
title: __unhook
description: 了解如何使用 Microsoft c + + extension 关键字 `__unhook` 进行本机事件处理。
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.openlocfilehash: 74f8b814ea23c5513b7b73bf90ef59984742a266
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483316"
---
# <a name="__unhook-keyword"></a>`__unhook` 关键字

将处理程序方法与事件解除。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>语法

```cpp
long  __unhook(
   &SourceClass::EventMethod,
   source,
   &ReceiverClass::HandlerMethod
   [, receiver = this]
);

long  __unhook(
   interface,
   source
);

long  __unhook(
   source
);
```

### <a name="parameters"></a>参数

*`&SourceClass::EventMethod`*\
指向从中解除挂钩事件处理程序方法的事件方法的指针：

- 本机 c + + 事件： *`SourceClass`* 是事件源类， *`EventMethod`* 是事件。

- COM 事件： *`SourceClass`* 是事件源接口， *`EventMethod`* 是其方法之一。

- 托管事件： *`SourceClass`* 是事件源类， *`EventMethod`* 是事件。

*`interface`*\
正在从 *接收器* 解除挂钩的接口名称，仅适用于 COM 事件接收器，其中属性的 *layout_dependent* 参数 [`event_receiver`](../windows/attributes/event-receiver.md) 是 **`true`** 。

*`source`*\
指向事件源的实例的指针。 根据 `type` 中指定的代码 `event_receiver` ， *source* 可以是以下类型之一：

- 本机事件源对象指针。

- `IUnknown` (COM 源) 的基于的指针。

- 托管对象指针（针对托管事件）。

*`&ReceiverClass::HandlerMethod`* 指向要从事件中解除挂钩的事件处理程序方法的指针。 处理程序被指定为类的方法或对相同的引用;如果未指定类名，则 **`__unhook`** 假定类是调用它的类。

- 本机 c + + 事件： *`ReceiverClass`* 是事件接收器类， `HandlerMethod` 是处理程序。

- COM 事件： *`ReceiverClass`* 是事件接收器接口， *`HandlerMethod`* 是它的一个处理程序。

- 托管事件： *`ReceiverClass`* 是事件接收器类， *`HandlerMethod`* 是处理程序。

*`receiver`* (可选) 指向事件接收器类的实例的指针。 如果未指定接收方，则默认值是调用的接收方类或结构 **`__unhook`** 。

## <a name="usage"></a>使用情况

可在任何函数范围内使用，包括 `main` 事件接收器类之外的。

## <a name="remarks"></a>注解

使用 **`__unhook`** 事件接收器中的内部函数将处理程序方法与事件方法解除关联。

有三种形式的 **`__unhook`** 。 在大多数情况下，可以使用第一种 (four-argument) 形式。 只能对 COM 事件接收器使用第二个 (参数) 形式，它将解除 **`__unhook`** 整个事件接口的挂钩。 可以使用第三种 (one-argument) 形式从指定的源中解除挂钩所有委托。

非零返回值指示已发生错误（托管事件将引发异常）。

如果对 **`__unhook`** 尚未挂钩的事件和事件处理程序调用，它将不起作用。

在编译时，编译器将验证事件是否存在，并利用指定的处理程序执行参数类型检查。

**`__hook`** **`__unhook`** 除了 COM 事件之外，还可以在事件接收器之外调用和。

使用的替代方法 **`__unhook`** 是使用-= 运算符。

有关新语法中的托管事件编码的信息，请参阅 [事件](../extensions/event-cpp-component-extensions.md)。

> [!NOTE]
> 模板类或结构不能包含事件。

## <a name="example"></a>示例

有关示例，请参阅 [本机 c + + 中的事件处理](../cpp/event-handling-in-native-cpp.md) 和 [COM 中的事件处理](../cpp/event-handling-in-com.md) 。

## <a name="see-also"></a>另请参阅

[字](../cpp/keywords-cpp.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__raise`](../cpp/raise.md)
