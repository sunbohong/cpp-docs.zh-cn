---
title: 'event_source (c + + COM 特性) '
description: 了解如何使用 Microsoft c + + 扩展 `event_source` COM 属性。
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.openlocfilehash: 3cdfaaa86f8fc36bf0dc90d7961077546362a662
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483264"
---
# <a name="event_source-attribute"></a>`event_source` 特性

创建事件源。

> [!NOTE]
> 本机 c + + 中的事件特性与标准 c + + 不兼容。 在指定一致性模式时，它们不会进行编译 [`/permissive-`](../../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>语法

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>参数

*`type`*\
以下值之一的枚举：

- `native` ，用于非托管 C/C++ 代码（非托管类的默认值）。

- `com` ，用于 COM 代码。 使用 `coclass` when *`type`* = `com` 。 此值需要包含以下头文件：

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`optimize`*\
当 *类型* 为时 `native` ，你可以指定 `optimize=size` ，以指示对于类中的所有事件 (最小) 值为4个字节的存储，或者 `optimize=speed` (默认) ，以指示存在4个 ( 个字节的事件) 字节的存储空间。

*`decorate`*\
当 *type* 为时 `native` ，你可以指定 `decorate=false` ，以指示合并的 (中的扩展名称 *`.mrg`*) 文件不应包含封闭类名称。 [`/Fx`](../../build/reference/fx-merge-injected-code.md) 允许你生成 *`.mrg`* 文件。 `decorate=false`（这是默认值）会导致合并文件中具有完全限定的类型名称。

## <a name="remarks"></a>注解

**`event_source`** C + + 属性指定应用它的类或结构将是事件源。

**`event_source`** 与 [`event_receiver`](event-receiver.md) 特性和关键字一起使用 [`__event`](../../cpp/event.md) 。 用于 `event_receiver` 创建事件接收器。 对 **`__event`** 事件源中的方法使用可将这些方法指定为事件。

> [!NOTE]
> 模板类或结构不能包含事件。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|--|--|
| **适用于** | **`class`**, **`struct`** |
| **且** | 否 |
| **必需属性** | **`coclass`** 即使 `type`=`com` |
| **无效的特性** | 无 |

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[编译器特性](compiler-attributes.md)\
[`event_receiver`](event-receiver.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[类特性](class-attributes.md)
