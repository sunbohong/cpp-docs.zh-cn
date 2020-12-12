---
description: 了解详细信息：表达式计算器错误 CXX0015
title: 表达式计算器错误 CXX0015
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: c5d6e0ba5407646b1e3c835053f1f115dabf4fe7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228321"
---
# <a name="expression-evaluator-error-cxx0015"></a>表达式计算器错误 CXX0015

表达式太复杂 (堆栈溢出) 

对于 C 表达式计算器可用的存储量，输入的表达式太复杂或嵌套太深。

由于挂起的计算过多，通常会发生溢出。

重新排列表达式，以便可以在表达式的每个组件遇到时进行计算，而不必等待表达式的其他部分计算。

将表达式拆分成多个命令。

此错误与 CAN0015 相同。
