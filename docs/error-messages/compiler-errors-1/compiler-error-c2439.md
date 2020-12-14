---
description: 了解更多：编译器错误 C2439
title: 编译器错误 C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: 6493fb634581646c20a8d856658fe728ae27364c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189803"
---
# <a name="compiler-error-c2439"></a>编译器错误 C2439

"identifier"：未能初始化成员

无法初始化类、结构或联合成员。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 尝试初始化间接基类或结构。

1. 尝试初始化类或结构的继承成员。 必须通过类或结构的构造函数来初始化继承的成员。
