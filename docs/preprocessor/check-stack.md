---
description: 详细了解 pragma Microsoft c/c + + 中的 check_stack 指令
title: check_stack pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragma, check_stack
- pragma, check_stack usage table
no-loc:
- pragma
ms.openlocfilehash: a395471625fed60fcf750ebac8f3159a89ba1487
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713709"
---
# <a name="check_stack-no-locpragma"></a>`check_stack` pragma

指示编译器在 **`off`** 指定 (或) 时关闭堆栈探测 **`-`** ，或在 **`on`** 指定 (或) 时打开堆栈探测 **`+`** 。

## <a name="syntax"></a>语法

> **`#pragma check_stack(`** [{ **`on`** | **`off`** }] **`)`**\
> **`#pragma check_stack`** { **`+`** | **`-`** }

## <a name="remarks"></a>注解

这 pragma 会在显示后在定义的第一个函数处生效 pragma 。 堆栈探测既不是宏的一部分也不是以内联方式生成的函数的一部分。

如果没有为 **`check_stack`** pragma 指定参数，堆栈检查将还原为在命令行上指定的行为。 有关详细信息，请参阅[编译器选项](../build/reference/compiler-options.md)。 `#pragma check_stack` [`/Gs`](../build/reference/gs-control-stack-checking-calls.md) 下表总结了和选项的交互。

### <a name="using-the-check_stack-pragma"></a>使用 check_stack 杂注

| 语法 | 是否使用<br /><br /> `/Gs` 选? | 操作 |
|--|--|--|
| `#pragma check_stack( )` 或<br /><br /> `#pragma check_stack` | 是 | 为后面的函数关闭堆栈检查 |
| `#pragma check_stack( )` 或<br /><br /> `#pragma check_stack` | 否 | 为后面的函数打开堆栈检查 |
| `#pragma check_stack(on)`<br /><br /> 或 `#pragma check_stack +` | 是或否 | 为后面的函数打开堆栈检查 |
| `#pragma check_stack(off)`<br /><br /> 或 `#pragma check_stack -` | 是或否 | 为后面的函数关闭堆栈检查 |

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
