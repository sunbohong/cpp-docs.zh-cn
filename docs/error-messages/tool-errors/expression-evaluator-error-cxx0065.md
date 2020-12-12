---
description: 了解详细信息：表达式计算器错误 CXX0065
title: 表达式计算器错误 CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: 8013bdc2541e2ab3719ef700413a87df49731983
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173163"
---
# <a name="expression-evaluator-error-cxx0065"></a>表达式计算器错误 CXX0065

变量需要堆栈帧

表达式包含当前范围内存在但尚未创建的变量。

当你逐步进入函数的 prolog 但尚未设置该函数的堆栈帧时，或者如果你逐步进入函数的退出代码，就会出现此错误。

单步执行序言代码，直到在计算表达式之前设置了堆栈帧。

此错误与 CAN0065 相同。
