---
description: 了解更多：编译器错误 C3397
title: 编译器错误 C3397
ms.date: 11/04/2016
f1_keywords:
- C3397
helpviewer_keywords:
- C3397
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
ms.openlocfilehash: 2d450e11849b58af55e34396674597fa3a60166d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313172"
---
# <a name="compiler-error-c3397"></a>编译器错误 C3397

默认参数中不允许进行聚合初始化

未正确声明数组。  有关详细信息，请参阅 [数组](../../extensions/arrays-cpp-component-extensions.md) 。

## <a name="example"></a>示例

下面的示例生成 C3397。

```cpp
// C3397.cpp
// compile with: /clr
// /clr /c
void Func(array<int> ^p = gcnew array<int> { 1, 2, 3 });   // C3397
void Func2(array<int> ^p = gcnew array<int> (3));   // OK

int main() {
   array<int> ^p = gcnew array<int> { 1, 2, 3};   // OK
}
```
