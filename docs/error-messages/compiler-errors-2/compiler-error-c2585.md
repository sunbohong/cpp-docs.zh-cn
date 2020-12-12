---
description: 了解更多：编译器错误 C2585
title: 编译器错误 C2585
ms.date: 11/04/2016
f1_keywords:
- C2585
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
ms.openlocfilehash: 568e5db1ca160b9fd13596d4f94f646cb4cf0bdd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177648"
---
# <a name="compiler-error-c2585"></a>编译器错误 C2585

到 "type" 的显式转换不明确

类型转换可能会产生多个结果。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 基于多个继承从类或结构类型转换。 如果该类型多次继承同一基类，则转换函数或运算符必须使用范围解析 (`::`) 来指定要在转换中使用的继承类。

1. 已定义转换运算符和构造函数进行相同的转换。
