---
description: 了解更多：预处理器指令
title: 预处理器指令
ms.date: 08/29/2019
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
ms.openlocfilehash: 016021fb21961e71b56a734941d6c495cc6f6741
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240515"
---
# <a name="preprocessor-directives"></a>预处理器指令

预处理器指令（如 `#define` 和 `#ifdef` ）通常用于使源程序在不同的执行环境中易于更改和编译。 源文件中的指令指示预处理器执行特定操作。 例如，预处理器可以替换文本中的标记，将其他文件的内容插入源文件，或通过移除几个部分的文本来取消一部分文件的编译。 在扩展宏之前，将识别并执行预处理器行。 因此，如果宏展开为类似于预处理器命令的内容，则预处理器无法识别它。

预处理器语句使用的字符集与源文件语句相同，但转义序列不受支持。 预处理器语句中使用的字符集与执行字符集相同。 预处理器还可识别负字符值。

预处理器可识别下列指令：

:::row:::
   :::column span="":::
      [`#define`](../preprocessor/hash-define-directive-c-cpp.md)\
      [`#elif`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#else`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#endif`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#error`](../preprocessor/hash-error-directive-c-cpp.md)\
      [`#if`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#ifdef`](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)\
      [`#ifndef`](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#import`](../preprocessor/hash-import-directive-cpp.md)\
      [`#include`](../preprocessor/hash-include-directive-c-cpp.md)\
      [`#line`](../preprocessor/hash-line-directive-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#pragma`](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
      [`#undef`](../preprocessor/hash-undef-directive-c-cpp.md)\
      [`#using`](../preprocessor/hash-using-directive-cpp.md)
   :::column-end:::
:::row-end:::

数字符号 (`#`) 必须是包含指令的行上的第一个非空白字符。 空格字符可以出现在指令的数字符号和第一个字母之间。 某些指令包含参数或值。 除了作为指令) 一部分的参数或值外 (指令后面的任何文本都必须以单行注释分隔符开头 (`//`) 或括在注释分隔符 (`/* */`) 。 包含预处理器指令的行可以通过紧靠在行尾标记前面，使用反斜杠 (`\`) 。

预处理器指令可以出现在源文件中的任意位置，但它们在显示后仅应用于源文件的其余部分。

## <a name="see-also"></a>请参阅

[预处理器运算符](../preprocessor/preprocessor-operators.md)\
[预定义的宏](../preprocessor/predefined-macros.md)\
[c/c + + 预处理器参考](../preprocessor/c-cpp-preprocessor-reference.md)
