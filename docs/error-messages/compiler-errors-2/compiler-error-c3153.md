---
description: 了解更多：编译器错误 C3153
title: 编译器错误 C3153
ms.date: 11/04/2016
f1_keywords:
- C3153
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
ms.openlocfilehash: 93b028e08963a8d124defe660966a75595c57771
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322041"
---
# <a name="compiler-error-c3153"></a>编译器错误 C3153

"interface"：不能创建接口的实例

接口不能实例化。 若要使用接口的成员，请从接口派生一个类，实现接口成员，然后使用成员。

下面的示例生成 C3153：

```cpp
// C3153.cpp
// compile with: /clr
interface class A {
};

int main() {
   A^ a = gcnew A;   // C3153
}
```
