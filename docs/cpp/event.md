---
title: __event
description: 了解如何使用 Microsoft c + + extension 关键字 `__event` 进行本机事件处理。
ms.date: 11/20/2020
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.openlocfilehash: 1678699d9b66c1a49dd5ca2bb019a6229c37a031
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483127"
---
# <a name="__event-keyword"></a>`__event` 关键字

声明事件。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>语法

> **`__event`** *`member-function-declarator`* **`;`**\
> **`__event`** **`__interface`** *`interface-specifier`* **`;`**\
> **`__event`** *`data-member-declarator`* **`;`**

## <a name="remarks"></a>注解

Microsoft 特定的关键字 **`__event`** 可应用于成员函数声明、接口声明或数据成员声明。 但是，不能使用 **`__event`** 关键字来限定嵌套类的成员。

根据您的事件源和接收器是本机 C++、COM 还是托管 (.NET Framework)，您可使用下列构造作为事件：

| 本机 C++ | COM | 托管 (.NET Framework) |
|--|--|--|
| 成员函数 | - | method |
| - | interface | - |
| - | - | 数据成员 (data member) |

[`__hook`](../cpp/hook.md)在事件接收器中使用将处理程序成员函数与事件成员函数相关联。 使用关键字创建事件后 **`__event`** ，在调用该事件时，将在之后调用该事件的所有事件处理程序。

**`__event`** 成员函数声明不能具有定义; 隐式生成定义，因此可以像调用任何普通成员函数一样调用事件成员函数。

> [!NOTE]
> 模板类或结构不能包含事件。

## <a name="native-events"></a>本机事件

本机事件是成员函数。 返回类型通常是 `HRESULT` 或 **`void`** ，但可以是任何整型类型，包括 **`enum`** 。 当某个事件使用整数返回类型时，如果事件处理程序返回非零值，则会定义错误条件。 在这种情况下，引发的事件将调用其他委托。

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

有关示例代码，请参阅 [本机 c + + 中的事件处理](../cpp/event-handling-in-native-cpp.md) 。

## <a name="com-events"></a>COM 事件

COM 事件是接口。 事件源接口中成员函数的参数应为 *in* 参数，但它不是严格强制执行的。 这是因为当多播时， *out* 参数不起作用。 如果使用 *out* 参数，则会发出1级警告。

返回类型通常是 `HRESULT` 或 **`void`** ，但可以是任何整型类型，包括 **`enum`** 。 当某个事件使用整数返回类型并且事件处理程序返回非零值时，这是一个错误条件。 引发的事件将中止对其他委托的调用。 编译器会将事件源接口自动标记为 [`source`](../windows/attributes/source-cpp.md) 生成的 IDL 中的。

[`__interface`](../cpp/interface.md)对于 COM 事件源，始终需要使用关键字 **`__event`** 。

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

有关代码示例，请参阅 [COM 中的事件处理](../cpp/event-handling-in-com.md) 。

## <a name="managed-events"></a>托管事件

有关新语法中的事件编码的信息，请参阅 [事件](../extensions/event-cpp-component-extensions.md)。

托管事件是数据成员或成员函数。 当与事件一起使用时，委托的返回类型必须符合 [公共语言规范](/dotnet/standard/language-independence-and-language-independent-components)。 事件处理程序的返回类型必须与委托的返回类型匹配。 有关委托的详细信息，请参阅 [委托和事件](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)。 如果托管事件是数据成员，则其类型必须是指向委托的指针。

在 .NET Framework 中，您可以将数据成员视为方法本身（即，其对应委托的 `Invoke` 方法）。 为此，请预定义用于声明托管事件数据成员的委托类型。 相反，托管事件方法会隐式定义相应的托管委托（如果尚未定义）。 例如，您可以将事件值（如 `OnClick`）声明为下面所示的事件：

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

隐式声明托管事件时，可以指定 `add` `remove` 在添加或删除事件处理程序时调用的和访问器。 你还可以定义成员函数，该函数从类的外部调用 (引发) 事件。

## <a name="example-native-events"></a>示例：本机事件

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>示例： COM 事件

```cpp
// EventHandling_COM_Event.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT MyEvent();
};
[ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]
class CSource : public IEventSource {
public:
   __event __interface IEventSource;
   HRESULT FireEvent() {
      __raise MyEvent();
      return S_OK;
   }
};
```

## <a name="see-also"></a>另请参阅

[字](../cpp/keywords-cpp.md)\
[事件处理](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
