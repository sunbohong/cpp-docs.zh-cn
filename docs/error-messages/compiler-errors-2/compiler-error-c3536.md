---
title: 编译器错误 C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: 2380a9d42525cfb662fa014b89751d6dc8b9f192
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508248"
---
# <a name="compiler-error-c3536"></a>编译器错误 C3536

"symbol"：初始化之前无法使用

指定的符号在初始化之前不能使用。 在实践中，这意味着无法使用变量来初始化自身。

### <a name="to-correct-this-error"></a>更正此错误

1. 不要使用自身初始化变量。

## <a name="example"></a>示例

下面的示例将生成 C3536，因为每个变量都是自行初始化的。

```cpp
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>请参阅

[auto 关键字](../../cpp/auto-cpp.md)
