---
description: 了解更多：编译器错误 C3166
title: 编译器错误 C3166
ms.date: 11/04/2016
f1_keywords:
- C3166
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
ms.openlocfilehash: c92883fec3fd68b969a6d357f8c3fab2f5a3aea1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242283"
---
# <a name="compiler-error-c3166"></a>编译器错误 C3166

> "指针"：不能将指向内部 __gc 指针的指针声明为 "type" 的成员

编译器找到了指向指针的指针 (的无效指针声明 **`__nogc`** **`__gc`** 。 ) 。

只能使用过时的编译器选项访问 C3166 **`/clr:oldSyntax`** 。
