---
description: 了解详细信息：编译器警告 (等级 1) C4627
title: 编译器警告（等级 1）C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: fc4c6c3931775b090dfd4c7c2fd5fd97441d40d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281439"
---
# <a name="compiler-warning-level-1-c4627"></a>编译器警告（等级 1）C4627

> "*header_file*"：在查找预编译头使用时跳过

如果当前源文件具有 [/Yu \( Use 预编译头文件) ](../../build/reference/yu-use-precompiled-header-file.md) 选项集，则编译器将在包含预编译标头之前忽略文件中的所有内容。 如果在预编译头文件之前包含了 *header_file* ，并且预编译标头不包含 *header_file*，则在 Visual Studio 2015 及更早版本中生成警告 **C4627** 。

## <a name="example"></a>示例

此示例演示如何发生此错误，并演示如何修复此错误：

```cpp
// c4627.cpp
#include <iostream>       // C4627 - iostream not included by pch.h
#include "pch.h"          // precompiled header file that does not include iostream
// #include <iostream>    // To fix, move the iostream header include here from above
int main()
{
    std::cout << "std::cout is defined!\n";
}
```

## <a name="see-also"></a>请参阅

[创建预编译标头文件](../../build/creating-precompiled-header-files.md)
