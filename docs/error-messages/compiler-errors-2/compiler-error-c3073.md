---
description: 了解更多：编译器错误 C3073
title: 编译器错误 C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: e26938d6c708c364bb2447b793abf7d51adb5779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320242"
---
# <a name="compiler-error-c3073"></a>编译器错误 C3073

"type"： ref 类没有用户定义的复制构造函数

在 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md) 编译时，编译器不会为引用类型生成复制构造函数。 在任何 **/clr** 编译中，如果需要复制类型的实例，则必须为引用类型定义自己的复制构造函数。

有关详细信息，请参阅 [引用类型的 c + + 堆栈语义](../../dotnet/cpp-stack-semantics-for-reference-types.md)。

## <a name="example"></a>示例

下面的示例生成 C3073。

```cpp
// C3073.cpp
// compile with: /clr
ref class R {
public:
   R(int) {}
};

ref class S {
public:
   S(int) {}
   S(const S %rhs) {}   // copy constructor
};

void f(R) {}
void f2(S) {}
void f3(R%){}

int main() {
   R r(1);
   f(r);   // C3073
   f3(r);   // OK

   S s(1);
   f2(s);   // OK
}
```
