---
description: 了解详细信息：符合杂注
title: conform 杂注
ms.date: 08/29/2019
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: bb9f62194196ea32e5f3326116894ea56ef83611
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300757"
---
# <a name="conform-pragma"></a>conform 杂注

**C++ 专用**

指定 [/zc： forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 编译器选项的运行时行为。

## <a name="syntax"></a>语法

> **#pragma 符合 (** *名称*[ **，show** ] [ **，** { **on**  |  **off** }] [[ **，** { **push**  |  **pop** }] [ **，** *标识符*[ **，** { **on**  |  **off** }]]] **)**

### <a name="parameters"></a>parameters

*路径名*\
指定要修改的编译器选项的名称。 唯一有效的 *名称* 为 `forScope` 。

**向**\
 (可选) 使 *名称* (true 或 false) 的当前设置在编译过程中通过警告消息显示。 例如 `#pragma conform(forScope, show)`。

**打开**、 **关闭**\
 (可选 *) 设置为* **on 时** 启用 [/zc： forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 编译器选项。 默认值为 **off**。

**请求**\
 (可选) 将 *name* 的当前值推送到内部编译器堆栈上。 如果指定 "*标识符*"，则可以为要推送到堆栈上的 *名称* 指定 "**开**" 或 "**关**" 值。 例如 `#pragma conform(forScope, push, myname, on)`。

**弹出**\
 (可选) 将 *name* 的值设置为内部编译器堆栈顶部的值，然后弹出堆栈。 如果用 **pop** 指定了标识符，则会弹出堆栈，直到找到具有 *标识符* 的记录，该记录也会被弹出;堆栈中的下一条记录的 *名称* 的当前值将成为 *name* 的新值。 如果指定 **pop** 时使用的 *标识符* 不在堆栈上的记录中，则将忽略 **pop** 。

*identifier*\
可以通过 **push** 或 **pop** 命令包含 (可选) 。 如果使用了 *标识符* ，则也可以使用 **on** 或 **off** 说明符。

## <a name="example"></a>示例

```cpp
// pragma_directive_conform.cpp
// compile with: /W1
// C4811 expected
#pragma conform(forScope, show)
#pragma conform(forScope, push, x, on)
#pragma conform(forScope, push, x1, off)
#pragma conform(forScope, push, x2, off)
#pragma conform(forScope, push, x3, off)
#pragma conform(forScope, show)
#pragma conform(forScope, pop, x1)
#pragma conform(forScope, show)

int main() {}
```

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
