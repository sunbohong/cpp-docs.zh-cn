---
title: 编译器警告（等级 4）C4932
description: 描述 Microsoft C/c + + 编译器警告 C4932。
ms.date: 08/25/2020
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: ece2ae14fd8e1198a97f5e772fcce52c47464878
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898287"
---
# <a name="compiler-warning-level-4-c4932"></a>编译器警告（等级 4）C4932

> `__identifier(identifier_1)` 和 `__identifier(identifier_2)` 不可区分

编译器无法将 **`_finally`** 和 **`__finally`** 或 **`__try`** 和 **`_try`** 视为传递到的参数 [`__identifier`](../../extensions/identifier-cpp-cli.md) 。 不要尝试在同一程序中将它们同时用作标识符，因为这将导致 [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) 错误。

下面的示例生成 C4932：

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
