---
description: 了解详细信息：编译器警告 (等级 1) C4228
title: 编译器警告（等级 1）C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: efb247d64ced8c44e84b8f3cfb4e15705eb57b1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266346"
---
# <a name="compiler-warning-level-1-c4228"></a>编译器警告（等级 1）C4228

使用了非标准扩展：忽略声明符列表中逗号后面的限定符

声明变量时使用逗号（如或后的限定符） **`const`** **`volatile`** 是 Microsoft 扩展 ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) 。

## <a name="example"></a>示例

```cpp
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```
