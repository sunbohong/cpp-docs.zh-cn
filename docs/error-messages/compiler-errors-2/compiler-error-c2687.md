---
description: 了解更多：编译器错误 C2687
title: 编译器错误 C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: 38996f2f31998ef96dd848915686adb1bf46c987
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220755"
---
# <a name="compiler-error-c2687"></a>编译器错误 C2687

"type"：异常声明不能为 "void"，也不能表示不完整类型或指向不完整类型的指针或引用

要使类型成为异常声明的一部分，必须定义该类型且该类型不是 void。

下面的示例生成 C2687：

```cpp
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

可能的解决方法：

```cpp
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```
