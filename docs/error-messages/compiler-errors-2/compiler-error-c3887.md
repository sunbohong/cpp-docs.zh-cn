---
description: 了解更多：编译器错误 C3887
title: 编译器错误 C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: 8c80a1ff54f56e111934ebc370fee28f011bd37b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274341"
---
# <a name="compiler-error-c3887"></a>编译器错误 C3887

"var"： literal 数据成员的初始值设定项必须是常量表达式

[Literal](../../extensions/literal-cpp-component-extensions.md)数据成员只能使用常量表达式进行初始化。

下面的示例生成 C3887：

```cpp
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

可能的解决方法：

```cpp
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```
