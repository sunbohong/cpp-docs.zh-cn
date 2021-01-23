---
description: 详细了解 pragma Microsoft c/c + + 中的 alloc_text 指令
title: alloc_text pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragma, alloc_text
no-loc:
- pragma
ms.openlocfilehash: f20cbf90952c6ac5793c5bdf4d2ef1c533be2126
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713124"
---
# <a name="alloc_text-no-locpragma"></a>`alloc_text` pragma

命名用于放置指定函数定义的代码部分。 pragma必须出现在函数声明符和命名函数的函数定义之间。

## <a name="syntax"></a>语法

> **`#pragma alloc_text(`** "*text-section*" **`,`** *function_1* [ **`,`** *function_2* ...] **`)`**

## <a name="remarks"></a>注解

**`alloc_text`** pragma 不处理 c + + 成员函数或重载函数。 它仅适用于用 C 链接声明的函数，即通过链接规范声明的函数 **`extern "C"`** 。 如果尝试对 pragma 具有 c + + 链接的函数使用此函数，则会生成编译器错误。

由于使用的函数寻址 **`__based`** 不受支持，因此，指定节位置需要使用 **`alloc_text`** pragma 。 *文本部分* 指定的名称应括在双引号中。

**`alloc_text`** pragma 必须出现在任何指定函数的声明之后和这些函数的定义之前。

中引用的函数 **`alloc_text`** pragma 应在与相同的模块中定义 pragma 。 否则，如果未定义的函数稍后编译为其他文本部分，则可能会捕获该错误，也可能不会捕获。 尽管程序通常会正常运行，但不会在预期的部分中分配函数。

对的其他限制 **`alloc_text`** 如下：

- 它不能在函数内使用。

- 必须在声明函数后且在定义函数前使用它。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
