---
description: 了解详细信息：编译器警告 (等级 1) C4087
title: 编译器警告（等级 1）C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: 2375ad5c99862f7ee8a0156ca1b3d637b95f0569
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267542"
---
# <a name="compiler-warning-level-1-c4087"></a>编译器警告（等级 1）C4087

“function”：用“void”参数列表声明

函数声明没有形参，而函数调用具有实参。 根据该函数的调用约定传递了额外的参数。

此警告针对 C 编译器。

## <a name="example"></a>示例

```c
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```
