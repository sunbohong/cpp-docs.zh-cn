---
description: 详细了解：编译器警告 (级别 4) C4673
title: 编译器警告（等级 4）C4673
ms.date: 11/04/2016
f1_keywords:
- C4673
helpviewer_keywords:
- C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
ms.openlocfilehash: 557a8a0049a5870b0ae824f96a96c12ee01c0842
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133999"
---
# <a name="compiler-warning-level-4-c4673"></a>编译器警告（等级 4）C4673

引发 "identifier" 不会在 catch 站点上考虑以下类型

无法在块中处理 throw 对象 **`catch`** 。 无法处理的每个类型都列在紧随包含此警告的行之后的错误输出中。 每个未处理的类型都有自己的警告。 有关详细信息，请阅读每个特定类型的警告。

下面的示例生成 C4673：

```cpp
// C4673.cpp
// compile with: /EHsc /W4
class Base {
private:
   char * m_chr;
public:
   Base() {
      m_chr = 0;
   }

   ~Base() {
      if(m_chr)
         delete m_chr;
   }
};

class Derv : private Base {
public:
   Derv() {}
   ~Derv() {}
};

int main() {
   try {
      Derv D1;
      // delete previous line, uncomment the next line to resolve
      // Base D1;
      throw D1;   // C4673
   }

   catch(...) {}
}
```
