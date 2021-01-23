---
description: 详细了解 pragma Microsoft c/c + + 中的 loop 指令
title: 圈 pragma
ms.date: 01/22/2021
f1_keywords:
- loop_CPP
- vc-pragma.loop
helpviewer_keywords:
- loop pragma
- pragma, loop
no-loc:
- pragma
ms.openlocfilehash: 4aac76cb5220e57dd378ac00ff576521c9001218
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713527"
---
# <a name="loop-no-locpragma"></a>`loop` pragma

控制自动并行如何考虑循环代码，或将循环排除在自动向量化的范围之外。

## <a name="syntax"></a>语法

> **`#pragma loop( hint_parallel(`***n***`) )`**\
> **`#pragma loop( no_vector )`**\
> **`#pragma loop( ivdep )`**

### <a name="parameters"></a>Parameters

**`hint_parallel(`***n***`)`**\
对编译器的提示：应跨 *n* 个线程并行化此循环，其中 *n* 是一个正整数文本或零。 如果 *n* 为零，则在运行时使用最大线程数。 这是对编译器的提示，而不是命令。 不保证会并行化循环。 如果循环具有数据依赖关系或结构问题，则不会对其进行并行化。 例如，如果存储到在循环体之外使用的标量，则不会对其进行并行化。

编译器会忽略此选项，除非 [`/Qpar`](../build/reference/qpar-auto-parallelizer.md) 指定编译器开关。

**`no_vector`**\
默认情况下，自动向量化尝试特征矢量化其评估的所有循环可能会从中受益。 指定此 pragma 项以禁用循环的自动向量化。

**`ivdep`**\
提示编译器忽略此循环的矢量依赖项的提示。

## <a name="remarks"></a>注解

若要使用 **`loop`** pragma ，请将它置于循环定义的前面，而不是。 在 pragma 其后的循环范围内生效。 可以按任意顺序将多个指令应用于 pragma 一个循环，但必须在单独的语句中声明每个指令 pragma 。

## <a name="see-also"></a>另请参阅

[自动并行化和自动矢量化](../parallel/auto-parallelization-and-auto-vectorization.md)\
[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
