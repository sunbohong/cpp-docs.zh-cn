---
title: '事件关键字 (c + +/CLI 和 c + +/CX) '
description: 了解如何使用 Microsoft c + + 组件扩展关键字 `event` 。
ms.date: 11/20/2020
ms.topic: reference
f1_keywords:
- event
- event_cpp
helpviewer_keywords:
- event keyword [C++]
ms.openlocfilehash: 6a2fa97140f747b4afc380b57f8f7c71f08875db
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483238"
---
# <a name="event-keyword-ccli-and-ccx"></a>`event` 关键字 (c + +/CLI 和 c + +/CX) 

**`event`** 关键字声明一个 *事件*，该事件是 (*事件处理程序* 的已注册订阅服务器的通知) 已发生的问题。

## <a name="all-runtimes"></a>所有运行时

C++/CX 支持声明事件成员或事件块。 事件成员是用于声明事件块的速记属性。 默认情况下，事件成员声明 `add`、`remove` 和 `raise` 函数，而这些函数将在事件块中显式声明。 若要自定义事件成员中的函数，请改为声明一个事件块，然后替代所需的函数。

### <a name="syntax"></a>语法

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>参数

*组合键*\
修饰符可用于事件声明或事件访问器方法。  可能的值为 **`static`** 和 **`virtual`** 。

*委托*\
签名必须与事件处理程序匹配的 [delegate](delegate-cpp-component-extensions.md)。

*event_name*\
事件的名称。

*return_value*\
事件访问器方法的返回值。  若要能验证，返回类型必须为 **`void`** 。

*parameters*\
（可选）`raise` 方法的参数，与 delegate 参数的签名匹配。

### <a name="remarks"></a>注解

事件是委托和 *事件处理程序* 之间的关联。 事件处理程序是在事件触发时进行响应的成员函数。 它允许来自任何类的客户端注册与委托的签名和返回类型相匹配的方法。

有两种类型的事件声明：

*事件数据成员*\
编译器会自动以委托类型成员的形式为事件创建存储空间，并创建内部 `add`、`remove` 和 `raise` 成员函数。 必须在类中声明事件数据成员。 委托的返回类型必须与事件处理程序的返回类型匹配。

*事件块*\
事件块可显式声明并自定义 `add`、`remove` 和 `raise` 方法的行为。

您可以使用 `operator +=` 和 `operator -=` 来添加和移除事件处理程序，或者显式调用 `add` 和 `remove` 方法。

**`event`** 是上下文相关的关键字。 有关详细信息，请参阅 [上下文相关的关键字](context-sensitive-keywords-cpp-component-extensions.md)。

## <a name="windows-runtime"></a>Windows 运行时

### <a name="remarks"></a>注解

有关详细信息，请参阅[事件 (C++/CX)](../cppcx/events-c-cx.md)。

若要添加和删除事件处理程序，请保存 `EventRegistrationToken` 由该操作返回的结构 `add` 。 然后在 `remove` 操作中，使用保存的 `EventRegistrationToken` 结构来识别要删除的事件处理程序。

### <a name="requirements"></a>要求

编译器选项：`/ZW`

## <a name="common-language-runtime"></a>公共语言运行时

使用 event 关键字，可以声明事件。 事件是类在相关事件发生时提供通知的一种方式。

### <a name="syntax"></a>语法

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>参数

*组合键*\
修饰符可用于事件声明或事件访问器方法。  可能的值为 **`static`** 和 **`virtual`** 。

*委托*\
签名必须与事件处理程序匹配的 [delegate](delegate-cpp-component-extensions.md)。

*event_name*\
事件的名称。

*return_value*\
事件访问器方法的返回值。  若要能验证，返回类型必须为 **`void`** 。

*parameters*\
（可选）`raise` 方法的参数，与 delegate 参数的签名匹配。

### <a name="remarks"></a>注解

事件是委托和 *事件处理程序* 之间的关联。 事件处理程序是在事件触发时进行响应的成员函数。 它允许来自任何类的客户端注册与基础委托的签名和返回类型相匹配的方法。

委托可以有一个或多个关联方法。 当你的代码指示事件已发生时，将调用这些方法。 程序中的事件可供面向 .NET Framework 公共语言运行时的其他程序使用。

有两种类型的事件声明：

*事件数据成员*\
编译器将数据成员事件的存储创建为委托类型的成员。 必须在类中声明事件数据成员。 它也称为 *普通事件*。 有关示例，请参阅代码示例。

*事件块*\
事件块允许 `add` `remove` `raise` 通过实现 `add` 、 `remove` 和 `raise` 方法来自定义、和方法的行为。 `add`、和方法的签名 `remove` `raise` 必须与委托的签名匹配。 事件块事件不是数据成员。 任何用作数据成员的都将生成编译器错误。

事件处理程序的返回类型必须与委托的返回类型匹配。

在 .NET Framework 中，您可以将数据成员视为方法本身（即，其对应委托的 `Invoke` 方法）。 为此，请预定义用于声明托管事件数据成员的委托类型。 相反，托管事件方法会隐式定义相应的托管委托（如果尚未定义）。 有关示例，请参阅本文末尾的代码示例。

在声明托管事件时，可以指定 `add` `remove` 在使用运算符和添加或移除事件处理程序时将调用的和访问 **`+=`** 器 **`-=`** 。 `add` `remove` `raise` 可以显式调用、和方法。

若要在 Microsoft c + + 中创建和使用事件，必须执行以下步骤：

1. 创建或标识委托。 如果要定义自己的事件，还必须确保有一个委托要用于 **`event`** 关键字。 例如，如果该事件在 .NET Framework 中进行了预定义，则该事件的使用者只需知道委托的名称。

2. 创建包括以下内容的类：

   - 从委托创建的事件。

   -  (可选) 一种方法，用于验证使用关键字声明的委托的实例 **`event`** 是否存在。 否则，此逻辑必须放在激发事件的代码中。

   - 调用此事件的方法。 这些方法可以替代一些基类功能。

   此类将定义该事件。

3. 定义一个或多个将方法连接到该事件的类。 其中每个类会将一个或多个方法与基类中的事件相关联。

4. 使用事件：

   - 创建包含事件声明的类的对象。

   - 创建包含事件定义的类的对象。

有关 c + +/CLI 事件的详细信息，请参阅 [接口中的事件](../dotnet/how-to-use-events-in-cpp-cli.md)。

### <a name="requirements"></a>要求

编译器选项：`/clr`

### <a name="examples"></a>示例

下面的代码示例演示如何声明委托、事件和事件处理程序对。 它演示了如何订阅 (添加) 、调用，然后取消订阅 (删除) 事件处理程序。

```cpp
// mcppv2_events.cpp
// compile with: /clr
using namespace System;

// declare delegates
delegate void ClickEventHandler(int, double);
delegate void DblClickEventHandler(String^);

// class that defines events
ref class EventSource {
public:
   event ClickEventHandler^ OnClick;   // declare the event OnClick
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick

   void FireEvents() {
      // raises events
      OnClick(7, 3.14159);
      OnDblClick("Hello");
   }
};

// class that defines methods that will called when event occurs
ref class EventReceiver {
public:
   void OnMyClick(int i, double d) {
      Console::WriteLine("OnClick: {0}, {1}", i, d);
   }

   void OnMyDblClick(String^ str) {
      Console::WriteLine("OnDblClick: {0}", str);
   }
};

int main() {
   EventSource ^ MyEventSource = gcnew EventSource();
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();

   // hook handler to event
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);

   // invoke events
   MyEventSource->FireEvents();

   // unhook handler to event
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);
}
```

```Output
OnClick: 7, 3.14159

OnDblClick: Hello
```

下面的代码示例演示了用于生成 `raise` 普通事件的方法的逻辑。 如果此事件有一个或多个订阅服务器，调用 `raise` 方法会隐式或显式调用委托。 如果委托的返回类型不是 **`void`** ，并且没有事件订阅服务器，则该 `raise` 方法将返回该委托类型的默认值。 如果没有事件订阅服务器，则调用 `raise` 方法会立即返回，并且不会引发异常。 如果委托返回类型不是 **`void`** ，则返回委托类型。

```cpp
// trivial_events.cpp
// compile with: /clr /c
using namespace System;
public delegate int Del();
public ref struct C {
   int i;
   event Del^ MyEvent;

   void FireEvent() {
      i = MyEvent();
   }
};

ref struct EventReceiver {
   int OnMyClick() { return 0; }
};

int main() {
   C c;
   c.i = 687;

   c.FireEvent();
   Console::WriteLine(c.i);
   c.i = 688;

   EventReceiver^ MyEventReceiver = gcnew EventReceiver();
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);
   Console::WriteLine(c.i);
}
```

```Output
0

688
```

## <a name="see-also"></a>另请参阅

[适用于 .NET 和 UWP 的组件扩展](component-extensions-for-runtime-platforms.md)
