---
description: 详细了解：编译器警告 (等级 2) C4094
title: 编译器警告 (等级 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: 63c554703c1eb6f7ecb831d1046641a0cde2094a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326526"
---
# <a name="compiler-warning-level-2-c4094"></a>编译器警告 (等级 2) C4094

未标记的 "token" 未声明符号

编译器检测到使用了未标记的结构、联合或类的空声明。 声明将被忽略。

## <a name="example"></a>示例

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

此条件在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 上生成错误。
