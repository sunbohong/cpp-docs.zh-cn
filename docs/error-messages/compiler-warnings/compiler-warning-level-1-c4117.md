---
description: 了解详细信息：编译器警告 (等级 1) C4117
title: 编译器警告（等级 1）C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 2c7b80c2e1a9e155e0196c2b62857d56877857b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267399"
---
# <a name="compiler-warning-level-1-c4117"></a>编译器警告（等级 1）C4117

保留“name”宏名；已忽略“Command”

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 尝试定义或取消定义预定义的宏。

1. 尝试定义或取消定义预处理器运算符 **defined**。

以下示例生成 C4117：

```cpp
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```
