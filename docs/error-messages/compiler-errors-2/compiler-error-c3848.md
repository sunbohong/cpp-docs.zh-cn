---
description: 了解更多：编译器错误 C3848
title: 编译器错误 C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 8bd81f59927dd1b34c23148dd1e9bd69ec715609
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255374"
---
# <a name="compiler-error-c3848"></a>编译器错误 C3848

类型为 "type" 的表达式会丢失一些常量可变限定符，以便调用 "function"

具有指定 const volatile 类型的变量只能调用使用相同或更大的 const volatile 限定定义的成员函数。

以下示例生成 C3848：

```cpp
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```
