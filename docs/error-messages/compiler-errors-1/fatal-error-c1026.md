---
description: 了解详细信息：严重错误 C1026
title: 错误 C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: 08816f21879cf6dfbeb0389700d9a8ffdc7a40d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345506"
---
# <a name="fatal-error-c1026"></a>错误 C1026

分析器堆栈溢出，程序太复杂

分析程序所需的空间导致了编译器堆栈溢出。

降低表达式的复杂性：

- 减小和语句中的嵌套 **`for`** **`switch`** 。 将更深层嵌套的语句置于单独的函数中。

- 分解涉及逗号运算符或函数调用的长表达式。
