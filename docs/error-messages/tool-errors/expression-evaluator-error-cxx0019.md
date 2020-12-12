---
description: 了解详细信息：表达式计算器错误 CXX0019
title: 表达式计算器错误 CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 1caf4714c1fc719883ee889c14225e4f69e961a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228230"
---
# <a name="expression-evaluator-error-cxx0019"></a>表达式计算器错误 CXX0019

错误的类型转换

C 表达式计算器无法按编写方式执行类型强制转换。

此错误与 CAN0019 相同。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 指定的类型未知。

1. 指针类型太多。 例如，类型转换

    ```
    (char **)h_message
    ```

   C 表达式计算器无法计算此值。
