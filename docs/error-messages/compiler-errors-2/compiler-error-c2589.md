---
description: 了解更多：编译器错误 C2589
title: 编译器错误 C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: b874988f65ef41a9cde19e4c0229a6cb54859b28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177492"
---
# <a name="compiler-error-c2589"></a>编译器错误 C2589

"identifier"： "：：" 右边的非法标记

如果类、结构或联合名称出现在范围解析运算符的左侧 (两个冒号) ，则右侧的标记必须是类、结构或联合成员。 否则，任何全局标识符都可以出现在右侧。

无法重载范围解析运算符。

下面的示例生成 C2589：

```cpp
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```
