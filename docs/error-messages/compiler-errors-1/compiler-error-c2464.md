---
description: 了解更多：编译器错误 C2464
title: 编译器错误 C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: 2e30166529616809478927dbfe6ff1f1efb3002a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341836"
---
# <a name="compiler-error-c2464"></a>编译器错误 C2464

"identifier"：不能使用 "new" 分配引用

使用运算符分配了引用标识符 **`new`** 。 引用不是内存对象，因此 **`new`** 无法返回指向它们的指针。 使用标准变量声明语法来声明引用。

下面的示例生成 C2464：

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
