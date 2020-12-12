---
description: 了解更多：编译器错误 C3274
title: 编译器错误 C3274
ms.date: 11/04/2016
f1_keywords:
- C3274
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
ms.openlocfilehash: 6706cc404bd6540aff7aa1afb94ada28249a0ade
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185734"
---
# <a name="compiler-error-c3274"></a>编译器错误 C3274

__finally/finally 没有匹配的 try

发现 [__finally](../../cpp/try-finally-statement.md) 或 [finally](../../dotnet/finally.md) 语句没有匹配的 **`try`** 。 若要解决此问题，请删除 **`__finally`** 语句或 **`try`** 为添加语句 **`__finally`** 。

以下示例生成 C3274：

```cpp
// C3274.cpp
// compile with: /clr
// C3274 expected
using namespace System;
int main() {
   try {
      try {
         throw gcnew ApplicationException();
      }
      catch(...) {
         Console::Error->WriteLine(L"Caught an exception");
      }
      finally {
         Console::WriteLine(L"In finally");
      }
   } finally {
      Console::WriteLine(L"In finally");
   }

   // Uncomment the following 3 lines to resolve.
   // try {
   //   throw gcnew ApplicationException();
   // }

   finally {
      Console::WriteLine(L"In finally");
   }
   Console::WriteLine(L"**FAIL**");
}
```
