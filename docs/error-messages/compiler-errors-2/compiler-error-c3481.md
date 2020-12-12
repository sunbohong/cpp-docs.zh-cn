---
description: 了解更多：编译器错误 C3481
title: 编译器错误 C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: 31f13b56a2b5df66a5765ee63313ffe265c15fe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113397"
---
# <a name="compiler-error-c3481"></a>编译器错误 C3481

“var”：未找到 lambda 捕获变量

编译器未找到传递给 lambda 表达式捕获列表的变量的定义。

### <a name="to-correct-this-error"></a>更正此错误

- 从 lambda 表达式的捕获列表中删除该变量。

## <a name="example"></a>示例

下面的示例由于未定义变量 `n` 而生成 C3481：

```cpp
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>请参阅

[Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)
