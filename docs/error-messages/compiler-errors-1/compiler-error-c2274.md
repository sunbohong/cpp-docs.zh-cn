---
description: 了解更多：编译器错误 C2274
title: 编译器错误 C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: 31b9d63b9cf87114ce2d1d79f1f38fff97d4ebbb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268348"
---
# <a name="compiler-error-c2274"></a>编译器错误 C2274

"type"： "." 运算符右侧的非法

类型显示为成员访问 ( ) 运算符的右操作数。

尝试访问用户定义的类型转换可能会导致此错误。 在 **`operator`** 句点和之间使用关键字 `type` 。

下面的示例生成 C2286：

```cpp
// C2274.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};

int main() {
   MyClass ClassName;
   int i = ClassName.int();   // C2274
   int j = ClassName.operator int();   // OK
}
```
