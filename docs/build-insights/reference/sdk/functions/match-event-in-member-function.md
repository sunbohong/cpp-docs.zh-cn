---
title: MatchEventInMemberFunction
description: C++ Build Insights SDK MatchEventInMemberFunction 函数参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 62a7bf6bde62dee7fdf5b1d2ce9044491a123f94
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920185"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInMemberFunction

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`MatchEventInMemberFunction` 函数用于将事件与成员函数的第一个参数所描述的类型进行匹配。 匹配的事件被转发给成员函数，以供进一步处理。

## <a name="syntax"></a>语法

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     TEvent,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventInMemberFunction(
    const RawEvent&          event,
    TInterface*              objectPtr,
    TReturn (TInterface::*   memberFunc)(TEvent, TExtraParams...),
    TExtraArgs&&...          extraArgs);
```

### <a name="parameters"></a>参数

TInterface\
包含成员函数的类型。

TReturn\
成员函数的返回类型。

TEvent\
要匹配的事件的类型。

TExtraParams\
成员函数接受的额外参数的类型，以及要匹配的事件类型。

TExtraArgs\
传递给 `MatchEventInMemberFunction` 的额外参数的类型。

*event*\
要与 TEvent 描述的事件类型进行匹配的事件。

objectPtr\
指向调用 memberFunc 的对象的指针。

memberFunc\
描述要匹配的事件类型的成员函数。

extraArgs\
与事件类型参数一起完美转发给 memberFunc 的参数。

### <a name="return-value"></a>返回值

如果匹配成功，则 `bool` 值为 `true`；否则，值为 `false`。

## <a name="remarks"></a>备注

可以从 Capture 类的列表中选择用于 TEvent 参数的事件类型。 有关事件以及可用于匹配它们的 Capture 类的列表，请参阅[事件表](../event-table.md)。

## <a name="example"></a>示例

```cpp
void MyClass::Foo1(Function f) {}

void MyClass::Foo2(Compiler cl) {}

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo1);

    bool b2 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo2);

    // b1: true because the first parameter of Foo1 is Function.
    // b2: false because the first parameter of Foo2 isn't Function.
}
```

::: moniker-end
