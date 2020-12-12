---
description: 了解更多：编译器错误 C2129
title: 编译器错误 C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: 5efb19aa3f4edd14dd6cfab93c3880745b08e59d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323150"
---
# <a name="compiler-error-c2129"></a>编译器错误 C2129

已声明但未定义静态函数 "function"

向从未定义的函数发出前向引用 **`static`** 。

**`static`** 必须在文件范围内定义函数。 如果该函数是在另一个文件中定义的，则必须将其声明为 **`extern`** 。
