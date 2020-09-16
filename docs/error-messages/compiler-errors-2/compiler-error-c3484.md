---
title: 编译器错误 C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: ded4a183f69e4903afb4c9dfeae22f7751ef76ad
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686275"
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
