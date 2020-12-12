---
description: 了解详细信息：表达式计算器错误 CXX0017
title: 表达式计算器错误 CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: 0abb99422383f95e13d4137a5ad899730d485f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228269"
---
# <a name="expression-evaluator-error-cxx0017"></a>表达式计算器错误 CXX0017

找不到符号

找不到表达式中指定的符号。

此错误的一个可能原因是符号名称不匹配。 因为 C 和 c + + 是区分大小写的语言，所以必须以其在源中定义的完全相同的形式提供符号名称。

尝试转换变量以在调试过程中监视变量时，可能会发生此错误。 为 `typedef` 类型声明新名称，但不定义新类型。 在调试器中尝试的转换需要定义的类型的名称。

此错误与 CAN0017 相同。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 请确保已在使用该符号的程序中的点声明符号。

1. 使用实际类型名称来强制转换调试器中的变量，而不是 `typedef` 定义的名称。
