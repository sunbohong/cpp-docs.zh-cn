---
description: 了解更多：编译器错误 C3279
title: 编译器错误 C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: c257a97cad1603703e7dbf2ed0d9f5cb3e6134a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258013"
---
# <a name="compiler-error-c3279"></a>编译器错误 C3279

不允许对在 cli 命名空间中声明的类模板进行部分专用化、显式专用化和显式实例化

`cli` 命名空间由 Microsoft 定义并包含伪模板。 Microsoft c + + 编译器不允许对此命名空间中的类模板进行用户定义的部分和显式专用化和显式实例化。

以下示例生成 C3279：

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
