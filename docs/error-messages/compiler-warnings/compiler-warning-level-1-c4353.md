---
description: 了解详细信息：编译器警告 (等级 1) C4353
title: 编译器警告（等级 1）C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 8842dccd617a0f5db81a0ce25a03b93f489f52ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311404"
---
# <a name="compiler-warning-level-1-c4353"></a>编译器警告（等级 1）C4353

使用了非标准扩展：常量0作为函数表达式。 改用 "__noop" 函数内部函数

不能将常量零 (0) 用作函数表达式。 有关详细信息，请参阅 [__noop](../../intrinsics/noop.md)。

下面的示例生成 C4353：

```cpp
// C4353.cpp
// compile with: /W1
void MyPrintf(void){};
#define X 0
#if X
   #define DBPRINT MyPrint
#else
   #define DBPRINT 0   // C4353 expected
#endif
int main(){
DBPRINT();
}
```
