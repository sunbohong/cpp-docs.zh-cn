---
description: 详细了解 pragma Microsoft c/c + + 中的 inline_depth 指令
title: inline_depth pragma
ms.date: 01/22/2021
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragma, inline_depth
- inline_depth pragma
no-loc:
- pragma
ms.openlocfilehash: 6daffdbcb598304925675c15c955941eb8369d23
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713566"
---
# <a name="inline_depth-no-locpragma"></a>`inline_depth` pragma

指定内联启发式搜索深度。 如果调用关系图中的函数深度超出了指定的值，则不会内联。

## <a name="syntax"></a>语法

> **`#pragma inline_depth(`** [ *n* ] **`)`**

## <a name="remarks"></a>注解

此 pragma 方法控制标记为和的函数的内联 [`inline`](../cpp/inline-functions-cpp.md) [`__inline`](../cpp/inline-functions-cpp.md) ，或自动内联到 **`/Ob`** 编译器选项下。 有关详细信息，请参阅[ `/Ob` (内联函数展开) ](../build/reference/ob-inline-function-expansion.md)。

*n* 可以是0到255之间的值，其中255表示调用关系图中的深度不受限制。 值0会禁止内联展开。 如果未指定 *n* ，则使用默认值254。

**`inline_depth`** pragma 控制可以扩展一系列函数调用的次数。 例如，假定内联深度为4。 如果 A 调用 B，然后 B 调用 C，则所有三个调用都将以内联方式展开。 但是，如果最近的内联深度展开为2，则只展开 A 和 B，C 将保留为函数调用。

若要使用此 pragma 选项，必须将 **`/Ob`** 编译器选项设置为1或更高版本。 使用这一设置的深度 pragma 在第一个函数调用之后生效 pragma 。

内联深度可以在扩展期间减少，但不会增加。 如果内联深度为6，在扩展期间，预处理器遇到 **`inline_depth`** pragma 值为8的，深度仍为6。

对标记为的 **`inline_depth`** pragma 函数不起作用 **`__forceinline`** 。

> [!NOTE]
> 可对递归函数进行内联替换，最大调用深度为 16。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)\
[`inline_recursion`](../preprocessor/inline-recursion.md)
