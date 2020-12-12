---
description: 了解更多：编译器错误 C3485
title: 编译器错误 C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 0b11eb4487a9b6deb611852dd11a8a1963dd961e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168379"
---
# <a name="compiler-error-c3485"></a>编译器错误 C3485

lambda 定义不能包含任何 cv 限定符

不能使用 **`const`** 或 **`volatile`** 限定符作为 lambda 表达式定义的一部分。

### <a name="to-correct-this-error"></a>更正此错误

- **`const`** **`volatile`** 从 lambda 表达式定义中删除或限定符。

## <a name="example"></a>示例

下面的示例生成 C3485，因为它使用 **`const`** 限定符作为 lambda 表达式定义的一部分：

```cpp
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>请参阅

[Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)
