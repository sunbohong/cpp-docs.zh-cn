---
description: 了解更多：编译器错误 C3495
title: 编译器错误 C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 3c04c80182dad32b539e09224fd9e303b3325578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113163"
---
# <a name="compiler-error-c3495"></a>编译器错误 C3495

“var”：lambda 捕获必须有自动存储持续时间

不能捕获没有自动存储持续时间的变量，如标记为或的变量 **`static`** **`extern`** 。

### <a name="to-correct-this-error"></a>更正此错误

- 不要将 **`static`** 或变量传递 **`extern`** 到 lambda 表达式的捕获列表。

## <a name="example"></a>示例

下面的示例生成 C3495，因为 **`static`** 变量 `n` 出现在 lambda 表达式的捕获列表中：

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>请参阅

[Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)
