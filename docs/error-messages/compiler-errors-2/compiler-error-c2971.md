---
description: 了解更多：编译器错误 C2971
title: 编译器错误 C2971
ms.date: 11/04/2016
f1_keywords:
- C2971
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
ms.openlocfilehash: 51cecf7fcf80b93231763bb183b870760820ca7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210382"
---
# <a name="compiler-error-c2971"></a>编译器错误 C2971

"class"：模板参数 "param"： "arg"：局部变量不能用作非类型参数

不能将本地变量的名称或地址用作模板参数。

下面的示例生成 C2971：

```cpp
// C2971.cpp
template <int *pi>
class Y {};

int global_var = 0;

int main() {
   int local_var = 0;
   Y<&local_var> aY;   // C2971
   // try the following line instead
   // Y<&global_var> aY;
}
```
