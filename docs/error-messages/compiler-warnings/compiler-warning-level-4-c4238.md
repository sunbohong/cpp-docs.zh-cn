---
description: 详细了解：编译器警告 (级别 4) C4238
title: 编译器警告（等级 4）C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: 8999d9ebeb4583256360f6223d4bf51a842fcb01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334872"
---
# <a name="compiler-warning-level-4-c4238"></a>编译器警告（等级 4）C4238

使用了非标准扩展：类 rvalue 用作了 lvalue

为了与早期版本的 Visual C++ 兼容，Microsoft extension (**/ze**) 允许在隐式或显式采用其地址的上下文中将类类型用作右值。 在某些情况下（例如以下示例），这可能很危险。

## <a name="example"></a>示例

```cpp
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

此用法会导致 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 下发生错误。
