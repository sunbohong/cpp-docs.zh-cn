---
title: 本机 C++ 中的事件处理
description: 了解如何使用 Microsoft c + + 扩展来处理本机 c + + 事件处理。
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: 5ad9128b7ff596674c3b08687b722c81b7a10aa8
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483173"
---
# <a name="event-handling-in-native-c"></a>本机 C++ 中的事件处理

在本机 c + + 事件处理中，使用[event_source](../windows/attributes/event-source.md)和[event_receiver](../windows/attributes/event-receiver.md)属性分别设置事件源和事件接收器，指定 `type` = `native` 。 这些属性允许应用它们的类在本机非 COM 上下文中激发事件和处理事件。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="declaring-events"></a>声明事件

在事件源类中，对 [`__event`](../cpp/event.md) 方法声明使用关键字，将方法声明为事件。 请确保声明方法，但不要定义它。 如果执行此操作，它会生成编译器错误，因为编译器在事件中进行了隐式定义。 本机事件可以是带有零个或多个参数的方法。 返回类型可以是 **`void`** 或任意整型。

## <a name="defining-event-handlers"></a>定义事件处理程序

在事件接收器类中，可定义事件处理程序。 事件处理程序是具有签名的方法， (返回类型、调用约定和与它们将处理的事件匹配的参数) 。

## <a name="hooking-event-handlers-to-events"></a>将事件处理程序挂钩到事件

此外，在事件接收器类中，可使用内部函数 [`__hook`](../cpp/hook.md) 将事件与事件处理程序关联，并将事件与 [`__unhook`](../cpp/unhook.md) 事件处理程序解除关联。 您可将多个事件挂钩到一个事件处理程序，或将多个事件处理程序挂钩到一个事件。

## <a name="firing-events"></a>触发事件

若要激发事件，请调用声明为事件源类中的事件的方法。 如果处理程序已挂钩到事件，则将调用处理程序。

### <a name="native-c-event-code"></a>本机 c + + 事件代码

以下示例演示如何在本机 C++ 中激发事件。 若要编译并运行此示例，请参考代码中的注释。 若要在 Visual Studio IDE 中生成代码，请确认 **`/permissive-`** 已关闭该选项。

## <a name="example"></a>示例

### <a name="code"></a>代码

```cpp
// evh_native.cpp
// compile by using: cl /EHsc /W3 evh_native.cpp
#include <stdio.h>

[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};

[event_receiver(native)]
class CReceiver {
public:
   void MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
   }

   void MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
   }

   void hookEvent(CSource* pSource) {
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void unhookEvent(CSource* pSource) {
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   CSource source;
   CReceiver receiver;

   receiver.hookEvent(&source);
   __raise source.MyEvent(123);
   receiver.unhookEvent(&source);
}
```

### <a name="output"></a>Output

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>请参阅

[事件处理](../cpp/event-handling.md)
