---
description: 详细了解：编译器警告 (级别 4) C4400
title: 编译器警告（等级 4）C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: c91a77758127b5c5b5c5ab742c980f6367830812
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136235"
---
# <a name="compiler-warning-level-4-c4400"></a>编译器警告（等级 4）C4400

"type"：不支持此类型上的 const/volatile 限定符

[Const](../../cpp/const-cpp.md)和[volatile](../../cpp/volatile-cpp.md)限定符不适用于公共语言运行时类型的变量。

## <a name="example"></a>示例

下面的示例生成 C4400。

```cpp
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```
