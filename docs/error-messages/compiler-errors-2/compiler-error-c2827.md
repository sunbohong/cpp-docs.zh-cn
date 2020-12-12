---
description: 了解更多：编译器错误 C2827
title: 编译器错误 C2827
ms.date: 11/04/2016
f1_keywords:
- C2827
helpviewer_keywords:
- C2827
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
ms.openlocfilehash: d9aae6fac1f21da2e1f4efad86024e11b94cf8e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194561"
---
# <a name="compiler-error-c2827"></a>编译器错误 C2827

不能用一元形式全局重写 "operator operator"

运算符不能在对象的外部具有一元形式。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 使重载运算符成为对象的局部变量。

1. 选择要重载的适当一元运算符。
