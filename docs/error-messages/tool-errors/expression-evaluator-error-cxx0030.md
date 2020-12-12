---
description: 了解详细信息：表达式计算器错误 CXX0030
title: 表达式计算器错误 CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: d9679d260ce81c2cb9bb8be4c082ffe8c1cfc6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237422"
---
# <a name="expression-evaluator-error-cxx0030"></a>表达式计算器错误 CXX0030

表达式 not evaluatable

调试器的表达式计算器无法获取所写入表达式的值。 其中一种可能的原因是，表达式引用的内存不在程序的地址空间内 (取消引用 null 指针是) 的一个示例。 Windows 不允许访问位于程序的地址空间以外的内存。

您可能想要使用括号重写表达式，以控制计算的顺序。

此错误与 CAN0030 相同。
