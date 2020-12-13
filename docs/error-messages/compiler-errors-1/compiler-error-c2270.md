---
description: 了解更多：编译器错误 C2270
title: 编译器错误 C2270
ms.date: 11/04/2016
f1_keywords:
- C2270
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
ms.openlocfilehash: 8c4d72c19b83ec60059775f8adeed35c381bd97e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336292"
---
# <a name="compiler-error-c2270"></a>编译器错误 C2270

"function"：非成员函数上不允许使用修饰符

非成员函数使用 [const](../../cpp/const-cpp.md)、 [volatile](../../cpp/volatile-cpp.md)或其他内存模型修饰符进行声明。

下面的示例生成 C2270：

```cpp
// C2270.cpp
// compile with: /c
void func1(void) const;   // C2270, nonmember function

void func2(void);

class CMyClass {
public:
   void func2(void) const;
};
```
