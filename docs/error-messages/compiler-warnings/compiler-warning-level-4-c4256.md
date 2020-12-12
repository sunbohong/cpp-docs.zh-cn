---
description: 详细了解：编译器警告 (级别 4) C4256
title: 编译器警告（等级 4）C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: 3ccd8447f930f40df5e488714cdcfb52e54d9928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189296"
---
# <a name="compiler-warning-level-4-c4256"></a>编译器警告（等级 4）C4256

"function"：具有虚拟基的类的构造函数具有 "...";调用可能与较旧版本的 Visual C++ 不兼容

可能的不兼容性。

请考虑以下代码示例。 如果在版本7之前使用 Microsoft c + + 编译器的版本编译了构造函数 S2：： S2 ( int i，... ) 的定义，但以下示例是使用当前版本编译的，则对 S3 的构造函数的调用将无法正常工作，因为有特殊的 case 调用约定更改。 如果两者都是使用 Visual C++ 6.0 编译的，该调用也无法完全正常工作，除非不为省略号传递任何参数。

若要修复此警告，

1. 不要在构造函数中使用省略号。

1. 请确保使用当前版本生成项目中的所有组件 (包括可以定义此类或引用此类) 的任何库，然后使用 [警告](../../preprocessor/warning.md) 杂注禁用此警告。

下面的示例生成 C4256：

```cpp
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```
