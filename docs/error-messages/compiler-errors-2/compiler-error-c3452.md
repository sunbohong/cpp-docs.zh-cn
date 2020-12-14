---
description: 了解更多：编译器错误 C3452
title: 编译器错误 C3452
ms.date: 11/04/2016
f1_keywords:
- C3452
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
ms.openlocfilehash: 7153088ccd132112f47823cd1eb1147480615fc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315980"
---
# <a name="compiler-error-c3452"></a>编译器错误 C3452

列出不是常量的参数成员

参数被传递到一个特性，但此特性需要一个常量，即一个在编译时可计算出结果的值。

## <a name="example"></a>示例

下面的示例生成 C3452。

```cpp
// C3452.cpp
// compile with: /c
int i;
[module( name="mod", type=dll, custom={i} ) ];   // C3452
// try the following line instead
// [module( name="mod", type=dll, custom={"a"} ) ];
```
