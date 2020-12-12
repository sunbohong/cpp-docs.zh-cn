---
description: 了解更多：编译器错误 C2828
title: 编译器错误 C2828
ms.date: 11/04/2016
f1_keywords:
- C2828
helpviewer_keywords:
- C2828
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
ms.openlocfilehash: 178b1998510d8119358d63ae0cf6f264efa6c9cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194548"
---
# <a name="compiler-error-c2828"></a>编译器错误 C2828

不能用 binary 形式全局重写 "operator operator"

运算符不能在对象的外部具有二进制形式。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 使重载运算符成为对象的局部变量。

1. 选择要重载的适当一元运算符。
