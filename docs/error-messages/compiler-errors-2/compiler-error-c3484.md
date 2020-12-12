---
description: 了解更多：编译器错误 C3484
title: 编译器错误 C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: 6d3e72ef89ad33333c840b549cfc5c7c40495130
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315681"
---
# <a name="compiler-error-c3484"></a>编译器错误 C3484

返回类型前应为“->”

你必须在 lambda 表达式的返回类型前提供 `->` 。

### <a name="to-correct-this-error"></a>更正此错误

- 在返回类型前提供 `->` 。

## <a name="examples"></a>示例

下面的示例生成 C3484：

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

下面的示例通过在 lambda 表达式的返回类型之前提供 `->` 来解决 C3484：

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>请参阅

[Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)
