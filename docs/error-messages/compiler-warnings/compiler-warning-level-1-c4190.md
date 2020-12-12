---
description: 了解详细信息：编译器警告 (等级 1) C4190
title: 编译器警告 (等级 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: ff27d5913e23fa1488816b3e2bb7284440c7577b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266580"
---
# <a name="compiler-warning-level-1-c4190"></a>编译器警告 (等级 1) C4190

"identifier1" 指定了 C 链接，但返回了与 C 不兼容的 UDT "identifier2"

函数或指向函数的指针具有 UDT (用户定义类型，该类型是类、结构、枚举或联合) 作为返回类型和 `extern "C"` 链接。 这是合法的：

- 对此函数的所有调用都是从 c + + 发生的。

- 函数的定义是在 c + + 中。

## <a name="example"></a>示例

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```
