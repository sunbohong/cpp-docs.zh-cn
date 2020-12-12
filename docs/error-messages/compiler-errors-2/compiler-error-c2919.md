---
description: 了解更多：编译器错误 C2919
title: 编译器错误 C2919
ms.date: 11/04/2016
f1_keywords:
- C2919
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
ms.openlocfilehash: 0e6498961fc5000897bcd9815c3cd3a6f90ecdfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270337"
---
# <a name="compiler-error-c2919"></a>编译器错误 C2919

“type”：不能在 WinRT 类型的发布接口上使用运算符

Windows 运行时类型系统不支持某类型的发布接口中的运算符成员函数。 这是因为并非所有语言都能使用运算符成员函数。 你可以创建可从相同类或编译单元中的 C++ 代码调用的私有或内部运算符成员函数。

要修复此问题，请将运算符成员函数从公共接口中删除，或将其更改为命名成员函数。 例如，将成员函数命名为 `Equals`，而不是使用 `operator==`。
