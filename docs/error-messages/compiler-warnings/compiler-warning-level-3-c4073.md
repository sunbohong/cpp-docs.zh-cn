---
description: 详细了解：编译器警告 (等级 3) C4073
title: 编译器警告 (等级 3) C4073
ms.date: 11/04/2016
f1_keywords:
- C4073
helpviewer_keywords:
- C4073
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
ms.openlocfilehash: a276dbb4c421eb828f80dde25bb2249e217e5df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208549"
---
# <a name="compiler-warning-level-3-c4073"></a>编译器警告 (等级 3) C4073

初始值设定项放置在库初始化区域中

只有第三方库开发人员应使用 [#pragma init_seg](../../preprocessor/init-seg.md)指定的库初始化区域。 下面的示例生成 C4073：

```cpp
// C4073.cpp
// compile with: /W3
#pragma init_seg(lib)   // C4073

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```
