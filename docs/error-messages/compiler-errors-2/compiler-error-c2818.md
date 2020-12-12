---
description: 了解更多：编译器错误 C2818
title: 编译器错误 C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: e258387af290a8070c1c66a56a7523b46482cf99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194782"
---
# <a name="compiler-error-c2818"></a>编译器错误 C2818

重载 "operator->" 的应用程序是通过类型 "type" 递归的

类成员访问运算符的重定义包含递归 **`return`** 语句。 若要 `->` 使用递归重新定义运算符，必须将递归例程移到从运算符 override 函数调用的单独函数。
