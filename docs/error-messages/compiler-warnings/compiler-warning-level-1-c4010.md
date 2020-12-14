---
description: 了解详细信息：编译器警告 (等级 1) C4010
title: 编译器警告 (等级 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 899e34e0835cce02ab5d11b6c64ae604369f93d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241581"
---
# <a name="compiler-warning-level-1-c4010"></a>编译器警告 (等级 1) C4010

单行注释包含行继续符

由//引入的单行注释包含 \\ 作为行继续符 () 的反斜杠。 编译器将下一行视为延续，并将其视为注释。

某些语法定向编辑器不将继续符后面的行指示为注释。 忽略导致此警告的任何行的语法着色。

下面的示例生成 C4010：

```cpp
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```
