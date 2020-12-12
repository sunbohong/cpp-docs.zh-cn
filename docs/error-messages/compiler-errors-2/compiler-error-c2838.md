---
description: 了解更多：编译器错误 C2838
title: 编译器错误 C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 70bc1fa038df33cfe63fccd7dc3db8983950b525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194392"
---
# <a name="compiler-error-c2838"></a>编译器错误 C2838

"member"：成员声明中的非法限定名

类、结构或联合使用完全限定名称重新声明另一类、结构或联合的成员。

下面的示例生成 C2838：

```cpp
// C2838.cpp
// compile with: /c
class Bellini {
public:
    void Norma();
};

class Bottesini {
   Bellini::Norma();  // C2838
};
```
