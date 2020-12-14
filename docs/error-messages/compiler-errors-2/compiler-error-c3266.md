---
description: 了解更多：编译器错误 C3266
title: 编译器错误 C3266
ms.date: 11/04/2016
f1_keywords:
- C3266
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
ms.openlocfilehash: 8522d893b6998be92a2b6241936481a7becb0c2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283634"
---
# <a name="compiler-error-c3266"></a>编译器错误 C3266

“class”：类-构造函数必须具有“void”参数列表

使用 /clr 编程的类中的类构造函数不能接受参数。

下面的示例生成 C3266：

```cpp
// C3266.cpp
// compile with: /clr

ref class X {
   static X(int i) { // C3266
   // try the following line instead
   // static X() {
   }
};

int main() {
}
```
