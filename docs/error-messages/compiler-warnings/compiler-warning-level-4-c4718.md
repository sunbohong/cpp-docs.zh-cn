---
description: 详细了解：编译器警告 (级别 4) C4718
title: 编译器警告（等级 4）C4718
ms.date: 11/04/2016
f1_keywords:
- C4718
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
ms.openlocfilehash: 9c0a24bbec0ae0cf902d905cc2dcecc492efc44b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330549"
---
# <a name="compiler-warning-level-4-c4718"></a>编译器警告（等级 4）C4718

“function call”：递归调用无副作用，正在删除

函数包含递归调用，但却没有副作用。 正在删除对此函数的调用。 不影响程序的正确性，而是影响其行为。 但保留该调用会导致运行时堆栈溢出异常，请删除该调用，从而排除这种可能性。
