---
description: 了解更多：编译器错误 C2337
title: 编译器错误 C2337
ms.date: 09/19/2019
f1_keywords:
- C2337
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
ms.openlocfilehash: 44def6fe9c220699e3687ce9b843f977528b5e15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234847"
---
# <a name="compiler-error-c2337"></a>编译器错误 C2337

> "*attribute-name*"：找不到属性

你的代码使用此上下文中不支持的属性。 或者，该特性在此版本的编译器中不可用。 若要解决此问题，请删除不支持的属性。

以下示例生成 C2337：

```cpp
// C2337.cpp
// compile with: /c
[emitidl];
[module(name="x")];
[grasshopper]   // C2337, not a supported attribute
class a{};
```
