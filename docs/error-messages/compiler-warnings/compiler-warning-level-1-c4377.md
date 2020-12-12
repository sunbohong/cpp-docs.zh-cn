---
description: 了解详细信息：编译器警告 (等级 1) C4377
title: 编译器警告（等级 1）C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: 674bfb69a20c901f20509a7359ed408b0e38f479
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185695"
---
# <a name="compiler-warning-level-1-c4377"></a>编译器警告（等级 1）C4377

本机类型默认为私有类型;-d1PrivateNativeTypes 已弃用

在以前的版本中，程序集中的本机类型在默认情况下是公开的，并且使用 (**/d1PrivateNativeTypes**) 的内部的未记录编译器选项来使其成为私有的。

默认情况下，所有类型（本机和 CLR）在程序集中都是私有的，因此不再需要 **/d1PrivateNativeTypes** 。

## <a name="example"></a>示例

下面的示例生成 C4377。

```cpp
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```
