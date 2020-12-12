---
description: 了解更多：编译器错误 C2170
title: 编译器错误 C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 2f6093221d214aa12f6b90f40dde14518e44e08e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322253"
---
# <a name="compiler-error-c2170"></a>编译器错误 C2170

"identifier"：未声明为函数，不能是内部函数

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 杂注用于 `intrinsic` 除函数之外的项。

1. Pragma `intrinsic` 用于无内部形式的函数。
