---
title: __raise
description: 了解如何使用 Microsoft c + + extension 关键字 `__raise` 进行本机事件处理。
ms.date: 11/20/2020
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.openlocfilehash: c9df602803062bc51b8c0cee13f17263cdc91786
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483135"
---
# <a name="__raise-keyword"></a>`__raise` 关键字

强调一个事件的调用站点。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>语法

> **`__raise`** *`method-declarator`* **`;`**

## <a name="remarks"></a>注解

在托管代码中，只能从定义事件的类中引发事件。 有关详细信息，请参阅 [`event`](../extensions/event-cpp-component-extensions.md)。

**`__raise`** 如果调用非事件，关键字会导致发出错误。

> [!NOTE]
> 模板类或结构不能包含事件。

## <a name="example"></a>示例

```cpp
// EventHandlingRef_raise.cpp
struct E {
   __event void func1();
   void func1(int) {}

   void func2() {}

   void b() {
      __raise func1();
      __raise func1(1);  // C3745: 'int Event::bar(int)':
                         // only an event can be 'raised'
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func1();
   __raise e.func1(1);  // C3745
   __raise e.func2();   // C3745
}
```

## <a name="see-also"></a>另请参阅

[字](../cpp/keywords-cpp.md)\
[事件处理](../cpp/event-handling.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[适用于 .NET 和 UWP 的组件扩展](../extensions/component-extensions-for-runtime-platforms.md)
