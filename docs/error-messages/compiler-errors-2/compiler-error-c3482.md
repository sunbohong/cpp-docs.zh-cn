---
description: 了解更多：编译器错误 C3482
title: 编译器错误 C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 752ce53b590ef5c10c25e0d0e850c7c4cc2776bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315694"
---
# <a name="compiler-error-c3482"></a>编译器错误 C3482

“this”只能在非静态成员函数中用作 lambda 捕获

不能将传递 **`this`** 给在静态方法或全局函数中声明的 lambda 表达式的捕获列表。

### <a name="to-correct-this-error"></a>更正此错误

- 将封闭函数转换为非静态方法，或

- **`this`** 从 lambda 表达式的捕获列表中删除指针。

## <a name="example"></a>示例

以下示例生成 C3482：

```cpp
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>请参阅

[Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)
