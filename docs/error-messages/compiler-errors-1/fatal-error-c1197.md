---
description: 了解详细信息：严重错误 C1197
title: 错误 C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: c61cbd71fa8f17dc787fd9ee5eabd0f073aafb39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268166"
---
# <a name="fatal-error-c1197"></a>错误 C1197

无法引用 "mscorlib.dll_1"，因为程序已经引用了 "mscorlib.dll_2"

编译器与公共语言运行时的版本匹配。  但是，尝试引用以前版本中的公共语言运行时文件的版本。

若要解决此错误，只需要从所编译的 Visual C++ 版本附带的公共语言运行时版本引用文件。

## <a name="example"></a>示例

下面的示例生成 C1197：

```cpp
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```
