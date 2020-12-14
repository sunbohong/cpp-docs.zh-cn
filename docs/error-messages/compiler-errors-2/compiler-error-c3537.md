---
description: 了解更多：编译器错误 C3537
title: 编译器错误 C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 84440b757b85a59f87fcca064911136da6cce269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315252"
---
# <a name="compiler-error-c3537"></a>编译器错误 C3537

"type"：不能强制转换为包含 "auto" 的类型

不能将变量强制转换为指定的类型，因为该类型包含 **`auto`** 关键字并且默认 [/zc： auto](../../build/reference/zc-auto-deduce-variable-type.md) 编译器选项有效。

## <a name="example"></a>示例

下面的代码将生成 C3537，因为这些变量将强制转换为包含关键字的类型 **`auto`** 。

```cpp
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>请参阅

[auto 关键字](../../cpp/auto-cpp.md)
