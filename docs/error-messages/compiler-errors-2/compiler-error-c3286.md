---
description: 了解更多：编译器错误 C3286
title: 编译器错误 C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 38e3b405f9093baa266cf56e5bfc7f44c7566206
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339228"
---
# <a name="compiler-error-c3286"></a>编译器错误 C3286

> "*说明符*"：迭代变量不能包含任何存储类说明符

不能对迭代变量指定存储类。 有关详细信息，请参阅 [ (c + +) 的存储类 ](../../cpp/storage-classes-cpp.md) 和 [中的每个](../../dotnet/for-each-in.md)存储类。

## <a name="example"></a>示例

下面的示例生成 C3286，并显示正确的用法。

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```
