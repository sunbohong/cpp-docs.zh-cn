---
description: 详细了解：编译器警告 (级别 4) C4516
title: 编译器警告（等级 4）C4516
ms.date: 11/04/2016
f1_keywords:
- C4516
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
ms.openlocfilehash: 945cf057b030a032afc2dd6dd3084df482f8a9a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241204"
---
# <a name="compiler-warning-level-4-c4516"></a>编译器警告（等级 4）C4516

"class：： symbol"：已弃用访问声明;成员 using 声明提供更好的替代方法

ANSI c + + 委员会已声明访问声明 (更改派生类中成员的访问权限，而无需 [使用](../../cpp/using-declaration.md) 关键字) 过期。 C + + 的未来版本可能不支持访问声明。

下面的示例生成 C4516：

```cpp
// C4516.cpp
// compile with: /W4
class A
{
public:
   void x(char);
};

class B : protected A
{
public:
   A::x;  // C4516 on access-declaration
   // use the following line instead
   // using A::x; // using-declaration, ok
};

int main()
{
}
```
