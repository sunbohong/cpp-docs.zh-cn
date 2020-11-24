---
title: 事件处理
description: 了解 Microsoft c + + 扩展如何支持 COM 和本机事件处理。
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: de8cd6dfac2b83e850ec62ff88e192d1c60e427e
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483121"
---
# <a name="event-handling"></a>事件处理

对于实现 COM 对象的 c + + 类，通常使用 ATL 类或 [coclass](../windows/attributes/coclass.md) 特性)  (com 类，主要支持事件处理。 有关详细信息，请参阅 [COM 中的事件处理](../cpp/event-handling-in-com.md)。

对于不实现 COM 对象) 的本机 c + + 类，还支持事件处理 (。 本机 c + + 事件处理支持已弃用，并将在将来的版本中删除。 有关详细信息，请参阅 [本机 c + + 中的事件处理](../cpp/event-handling-in-native-cpp.md)。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

事件处理支持单线程和多线程用法。 它可防止数据同时进行多线程访问。 可以从事件源或接收方类派生子类。 这些子类支持扩展事件源和接收。

Microsoft c + + 编译器包含用于声明事件和事件处理程序的属性和关键字。 事件特性和关键字可用于 CLR 程序和本机 C++ 程序中。

| 文章 | 说明 |
|--|--|
| [`event_source`](../windows/attributes/event-source.md) | 创建事件源。 |
| [`event_receiver`](../windows/attributes/event-receiver.md) | 创建事件接收器（接收器）。 |
| [`__event`](../cpp/event.md) | 声明事件。 |
| [`__raise`](../cpp/raise.md) | 强调一个事件的调用站点。 |
| [`__hook`](../cpp/hook.md) | 将处理程序方法与事件关联。 |
| [`__unhook`](../cpp/unhook.md) | 将处理程序方法与事件解除。 |

## <a name="see-also"></a>另请参阅

[C++ 语言参考](../cpp/cpp-language-reference.md)\
[关键字](../cpp/keywords-cpp.md)
