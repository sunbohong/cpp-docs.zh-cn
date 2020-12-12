---
description: 了解更多：编译器错误 C2854
title: 编译器错误 C2854
ms.date: 11/04/2016
f1_keywords:
- C2854
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
ms.openlocfilehash: beb4947e365d1a64d5b0c8ad5ffcdf647b0939d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260132"
---
# <a name="compiler-error-c2854"></a>编译器错误 C2854

#pragma hdrstop 中的语法错误

`#pragma hdrstop`提供了无效的文件名。 杂注后面可以跟一个可选的文件名，用括号和引号引起来：

下面的示例生成 C2854：

```cpp
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```
