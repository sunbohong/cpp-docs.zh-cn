---
description: 了解更多：预处理器运算符
title: 预处理器运算符
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 960531a32dd8b4f834117fb01272e2ed45fecf92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202088"
---
# <a name="preprocessor-operators"></a>预处理器运算符

在指令的上下文中使用四个预处理器特定运算符 `#define` 。 请参阅下表了解每个。 接下来的三个部分讨论了字符串化、charizing 和标记粘贴运算符。 有关运算符的信息 `defined` ，请参阅 [#if、#elif、#else 和 #endif 指令](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)。

|操作员|操作|
|--------------|------------|
|[字符串化运算符 (#)](../preprocessor/stringizing-operator-hash.md)|导致将相应的实参括在双引号中|
|[字符化运算符 (#@)](../preprocessor/charizing-operator-hash-at.md)|导致相应的参数括在单引号中，并被视为 (特定于 Microsoft 的) |
|[标记粘贴运算符 (##)](../preprocessor/token-pasting-operator-hash-hash.md)|允许用于连接到其他标记的实参的标记|
|[定义的运算符](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|简化某些宏指令中的复合表达式的编写|

## <a name="see-also"></a>请参阅

[预处理器指令](../preprocessor/preprocessor-directives.md)\
[预定义的宏](../preprocessor/predefined-macros.md)\
[c/c + + 预处理器参考](../preprocessor/c-cpp-preprocessor-reference.md)
