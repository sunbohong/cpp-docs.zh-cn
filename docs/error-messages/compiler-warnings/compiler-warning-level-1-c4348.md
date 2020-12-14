---
description: 了解详细信息：编译器警告 (等级 1) C4348
title: 编译器警告（等级 1）C4348
ms.date: 11/04/2016
f1_keywords:
- C4348
helpviewer_keywords:
- C4348
ms.assetid: 816010eb-6079-48d5-a41b-0fc4d67cfe4c
ms.openlocfilehash: 279281b6a060876255e6b258cf4de4fb7e9b3aff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311430"
---
# <a name="compiler-warning-level-1-c4348"></a>编译器警告（等级 1）C4348

"type"：重定义默认参数：参数号

重新定义了模板参数。

下面的示例生成 C4348：

```cpp
// C4348.cpp
// compile with: /LD /W1
template <class T=int> struct A;   // forward declaration

template <class T=int> struct A { };
// C4348, redefinition of default parameter
// try the following line instead
// template <class T> struct A { };
```
