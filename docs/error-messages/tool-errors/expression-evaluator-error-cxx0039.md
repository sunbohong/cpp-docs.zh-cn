---
description: 了解详细信息：表达式计算器错误 CXX0039
title: 表达式计算器错误 CXX0039
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 19d8e01e3eb8f599319988a8aa9fc0bf401701fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244727"
---
# <a name="expression-evaluator-error-cxx0039"></a>表达式计算器错误 CXX0039

符号不明确

C 表达式计算器无法确定要在表达式中使用的符号实例。 符号在继承树中出现多次。

必须使用范围解析运算符 (`::`) 显式指定要在表达式中使用的实例。

此错误与 CAN0039 相同。
