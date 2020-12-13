---
description: 了解更多：编译器错误 C2410
title: 编译器错误 C2410
ms.date: 11/04/2016
f1_keywords:
- C2410
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
ms.openlocfilehash: 921ccdcff64bca28c3a771dd0931b8b7abf83e52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341888"
---
# <a name="compiler-error-c2410"></a>编译器错误 C2410

"identifier"： "context" 中的成员名称不明确

标识符是此上下文中多个结构或联合的成员。

对导致错误的操作数使用结构或联合说明符。 结构或联合说明符是类型的标识符， **`struct`** 或者 **`union`** (与 **`typedef`**) 引用的结构或联合类型相同的名称或变量。 说明符必须是第一个成员选择运算符 ( 的左操作数，) 才能使用操作数。
