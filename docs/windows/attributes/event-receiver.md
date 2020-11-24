---
title: 'event_receiver (c + + COM 特性) '
description: 了解如何使用 Microsoft c + + 扩展 `event_receiver` COM 属性。
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.openlocfilehash: 8ed6ef6113d72a9565b275dff4e035dc56f11e82
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483277"
---
# <a name="event_receiver-attribute"></a>`event_receiver` 特性

创建事件接收器（接收器）。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>语法

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>参数

*`type`*\
以下值之一的枚举：

- `native` 对于非托管 C/c + + 代码 (本机类) 的默认值。

- `com` ，用于 COM 代码。 此值需要包含以下头文件：

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`layout_dependent`*\
*`layout_dependent`* 仅在 com 上指定 `type` = **com**。 *`layout_dependent`* 是一个布尔值：

- **`true`** 表示事件接收方中的委托签名必须与它们在事件源中挂钩到的委托的签名完全匹配。 事件接收器处理程序名称必须与相关事件源接口中指定的名称相匹配。 `coclass`当为时使用 *`layout_dependent`* **`true`** 。 指定的效率稍有提高 **`true`** 。

- **`false`** (默认) 意味着调用约定和存储类 (`virtual` 、 `static` 和其他) 不必与事件方法和处理程序匹配。 处理程序名称还不需要与事件源接口方法名称匹配。

## <a name="remarks"></a>注解

**`event_receiver`** C + + 属性指定应用它的类或结构将是事件接收器，并使用 Microsoft c + + 统一事件模型。

**`event_receiver`** 与 [`event_source`](event-source.md) 特性和和关键字一起使用 [`__hook`](../../cpp/hook.md) [`__unhook`](../../cpp/unhook.md) 。 用于 `event_source` 创建事件源。 **`__hook`** 在事件接收器的方法中使用，将 ( "挂钩" ) 事件接收器方法与事件源的事件关联。 使用取消 **`__unhook`** 关联。

*`layout_dependent`* 仅为 COM 事件接收器指定 (`type` = **`com`**) 。 的默认值 *`layout_dependent`* 为 **`false`** 。

> [!NOTE]
> 模板类或结构不能包含事件。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|--|--|
| **适用于** | **`class`**, **`struct`** |
| **且** | 否 |
| **必需属性** | `coclass` 即使 *`layout_dependent`*=**`true`** |
| **无效的特性** | 无 |

有关详细信息，请参阅 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[编译器特性](compiler-attributes.md)\
[`event_source`](event-source.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[类特性](class-attributes.md)
