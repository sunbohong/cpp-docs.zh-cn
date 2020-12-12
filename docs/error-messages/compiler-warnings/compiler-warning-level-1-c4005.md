---
description: 了解详细信息：编译器警告 (等级 1) C4005
title: 编译器警告 (等级 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: a8de4974d87eb5d8396085bb79dfbfe14a177602
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325982"
---
# <a name="compiler-warning-level-1-c4005"></a>编译器警告 (等级 1) C4005

"identifier"：宏重定义

宏标识符定义了两次。 编译器使用第二个宏定义。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 使用指令在命令行和代码中定义宏 `#define` 。

1. 从包含文件导入的宏。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 删除其中一个定义。

1. 在第二个定义前使用 [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) 指令。

下面的示例生成 C4005：

```cpp
// C4005.cpp
// compile with: /W1 /EHsc
#include <iostream>
using namespace std;

#define TEST "test1"
#define TEST "test2"   // C4005 delete or rename to resolve the warning

int main() {
   cout << TEST << endl;
}
```
