---
title: 编译器错误 C2725
ms.date: 11/04/2016
f1_keywords:
- C2725
helpviewer_keywords:
- C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
ms.openlocfilehash: b2e8c6a2d3368e2f7fc1277e3bf727848da50881
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741392"
---
# <a name="compiler-error-c2725"></a>编译器错误 C2725

“exception”：无法根据值或引用引发或捕获托管或 WinRT 对象

托管或 WinRT 异常的类型不正确。

## <a name="examples"></a>示例

下面的示例生成 C2725，并演示如何修复此错误。

```cpp
// C2725.cpp
// compile with: /clr
ref class R {
public:
   int i;
};

int main() {
   R % r1 = *gcnew R;
   throw r1;   // C2725

   R ^ r2 = gcnew R;
   throw r2;   // OK
}
```

下面的示例生成 C2725，并演示如何修复此错误。

```cpp
// C2725b.cpp
// compile with: /clr
using namespace System;
int main() {
   try {}
   catch( System::Exception%) {}   // C2725
   // try the following line instead
   // catch( System::Exception ^e) {}
}
```
