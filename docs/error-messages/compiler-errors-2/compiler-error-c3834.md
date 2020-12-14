---
description: 了解更多：编译器错误 C3834
title: 编译器错误 C3834
ms.date: 11/04/2016
f1_keywords:
- C3834
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
ms.openlocfilehash: 4cf0bc5e3587e77d8ad31fc4e2fd2cf0130aa781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249173"
---
# <a name="compiler-error-c3834"></a>编译器错误 C3834

非法显式转换为钉住指针;改为使用固定的本地变量

不允许显式转换为固定指针。

## <a name="example"></a>示例

下面的示例生成 C3834。

```cpp
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
