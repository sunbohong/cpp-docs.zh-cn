---
title: 编译器错误 C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: cfd2aa6f10b6e43ed10135ea2b6801619176cff5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508182"
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
