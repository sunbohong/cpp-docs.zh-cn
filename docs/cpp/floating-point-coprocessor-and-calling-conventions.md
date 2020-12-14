---
description: 了解详细信息：浮点协处理器和调用约定
title: 浮点协处理器和调用约定
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 2f68671783b8a556e787aa6637b9b5c2e5799485
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242543"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮点协处理器和调用约定

如果要为浮点协处理器编写程序集例程，则必须保留浮点控制字并清理协处理器堆栈，除非你返回的是 **`float`** 或 **`double`** 值 (函数应在 ST (0 中返回) # A3。

## <a name="see-also"></a>请参阅

[调用约定](../cpp/calling-conventions.md)
