---
description: 了解详细信息：编译器警告 (等级 1) C4441
title: 编译器警告（等级 1）C4441
ms.date: 11/04/2016
f1_keywords:
- C4441
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
ms.openlocfilehash: f09e25696edffadaeb843d0dbb7ec47f4bcf8a49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212566"
---
# <a name="compiler-warning-level-1-c4441"></a>编译器警告（等级 1）C4441

已忽略 "cc1" 的调用约定;改为使用 "cc2"

托管用户定义类型中的成员函数和全局函数泛型必须使用 [__clrcall](../../cpp/clrcall.md) 调用约定。  使用的编译器 `__clrcall` 。

## <a name="example"></a>示例

下面的示例生成 C4441。

```cpp
// C4441.cpp
// compile with: /clr /W1 /c
generic <class ItemType>
void __cdecl Test(ItemType item) {}   // C4441
// try the following line instead
// void Test(ItemType item) {}

ref struct MyStruct {
   void __cdecl Test(){}   // C4441
   void Test2(){}   // OK
};
```
