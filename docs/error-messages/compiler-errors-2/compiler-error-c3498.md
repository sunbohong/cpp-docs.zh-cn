---
title: 编译器错误 C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: f1b978a585f3404cd3a881f25d6ef6a0f66b212d
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686150"
---
# <a name="compiler-error-c3498"></a>编译器错误 C3498

"var"：无法捕获具有托管或 WinRTtype 的变量

无法在 lambda 中捕获具有托管类型或 Windows 运行时类型的变量。

### <a name="to-correct-this-error"></a>更正此错误

- 将托管或 Windows 运行时变量传递到 lambda 表达式的参数列表。

## <a name="examples"></a>示例

下面的示例将生成 C3498，因为 lambda 表达式的捕获列表中出现了具有托管类型的变量：

```cpp
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

下面的示例通过将托管变量 `s` 传递到 lambda 表达式的参数列表，解决了 C3498：

```cpp
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>请参阅

[Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)
