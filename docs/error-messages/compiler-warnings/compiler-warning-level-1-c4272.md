---
description: 了解详细信息：编译器警告 (等级 1) C4272
title: 编译器警告（等级 1）C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: a44e3a4121c1d01b15af47b0b4eefb1f982423bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266112"
---
# <a name="compiler-warning-level-1-c4272"></a>编译器警告（等级 1）C4272

"function"：标记为 __declspec (dllimport) ;导入函数时必须指定本机调用约定。

导出使用 [__clrcall](../../cpp/clrcall.md) 调用约定标记的函数是错误的，如果尝试导入标记为的函数，编译器会发出此警告 `__clrcall` 。

下面的示例生成 C4272：

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
