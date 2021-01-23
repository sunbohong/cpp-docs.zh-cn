---
description: 详细了解 pragma Microsoft c/c + + 中的符合指令
title: 符合 pragma
ms.date: 01/22/2021
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragma, conform
no-loc:
- pragma
ms.openlocfilehash: baaeb41e2364daac8de91ca15251226bf3dd1e2a
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713696"
---
# <a name="conform-no-locpragma"></a>`conform` pragma

**C++ 专用**

指定编译器选项的运行时行为 [`/Zc:forScope`](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 。

## <a name="syntax"></a>语法

> **`#pragma conform(`***name* [ **`, show`** ] [ **`,`** { **`on`**  |  **`off`** }] [[ **`,`** { **`push`**  |  **`pop`** }] [ **`,`** *标识符*[ **`,`** { **`on`**  |  **`off`** }]]]**`)`**

### <a name="parameters"></a>Parameters

*路径名*\
指定要修改的编译器选项的名称。 唯一有效的 *名称* 为 `forScope` 。

**`show`**\
 (可选) 使 *名称* (true 或 false) 的当前设置在编译过程中通过警告消息显示。 例如，`#pragma conform(forScope, show)`。

**`on`**, **`off`**\
 (可选) 设置 *名称* 以 **`on`** 启用 [/zc： forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 编译器选项。 默认值为 **`off`** 。

**`push`**\
 (可选) 将 *name* 的当前值推送到内部编译器堆栈上。 如果指定 *标识符*，则可以为 **`on`** **`off`** 要推送到堆栈的 *名称* 指定或值。 例如，`#pragma conform(forScope, push, myname, on)`。

**`pop`**\
 (可选) 将 *name* 的值设置为内部编译器堆栈顶部的值，然后弹出堆栈。 如果为指定了标识符 **`pop`** ，则将向后弹出堆栈，直到找到具有 *标识符* 的记录（这也会被弹出）; 堆栈上的下一条记录中的 *名称* 的当前值将成为新的 *name* 值。 如果指定的 **`pop`** *标识符* 不在堆栈上的记录中，则 **`pop`** 将忽略。

*identifier*\
 (可选的) 可以包含在 **`push`** 或 **`pop`** 命令中。 如果使用了 *标识符* ，则 **`on`** **`off`** 也可以使用或说明符。

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

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
