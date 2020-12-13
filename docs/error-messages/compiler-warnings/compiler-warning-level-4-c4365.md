---
description: 详细了解：编译器警告 (级别 4) C4365
title: 编译器警告（等级 4）C4365
ms.date: 11/04/2016
f1_keywords:
- C4365
helpviewer_keywords:
- C4365
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
ms.openlocfilehash: d7316e6b32bd90b95f5f9277a565455733185d72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330618"
---
# <a name="compiler-warning-level-4-c4365"></a>编译器警告（等级 4）C4365

"action"：从 "type_1" 转换到 "type_2"，有符号/无符号不匹配

例如，你尝试将无符号值转换为有符号的值。

默认情况下，C4365 处于关闭状态。  有关详细信息，请参阅 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

## <a name="example"></a>示例

下面的示例生成 C4365。

```cpp
// C4365.cpp
// compile with: /W4
#pragma warning(default:4365)

int f(int) { return 0; }
void Test(size_t i) {}

int main() {
   unsigned int n = 10;
   int o = 10;
   n++;
   f(n);   // C4365
   f(o);   // OK

   Test( -19 );   // C4365
}
```
