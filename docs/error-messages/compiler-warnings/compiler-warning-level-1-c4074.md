---
description: 了解详细信息：编译器警告 (等级 1) C4074
title: 编译器警告 (等级 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: cb04b242415769e995a46a9cdf3e0dff827ec1db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267620"
---
# <a name="compiler-warning-level-1-c4074"></a>编译器警告 (等级 1) C4074

初始值设定项放置在编译器保留的初始化区域中

由 Microsoft 保留 [#pragma init_seg](../../preprocessor/init-seg.md)指定的编译器初始化区域。 此区域中的代码可在 C 运行库的初始化之前执行。

下面的示例生成 C4074：

```cpp
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```
