---
description: 了解更多：编译器错误 C2657
title: 编译器错误 C2657
ms.date: 11/04/2016
f1_keywords:
- C2657
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
ms.openlocfilehash: dfec399c4b65615310263aa58db145b87c42594d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286067"
---
# <a name="compiler-error-c2657"></a>编译器错误 C2657

在语句的开始找到 "class：:*" (是否忘记指定类型？ ) 

该行以指向成员的指针标识符开头。

如果指向成员的指针的声明中缺少类型说明符，则可能导致此错误。

下面的示例生成 C2657：

```cpp
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```
