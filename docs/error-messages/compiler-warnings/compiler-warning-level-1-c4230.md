---
description: 了解详细信息：编译器警告 (等级 1) C4230
title: 编译器警告（等级 1）C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: b5427d4ab87a1ba1c65456dab379f76100e75fea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266282"
---
# <a name="compiler-warning-level-1-c4230"></a>编译器警告（等级 1）C4230

使用了记时错误：修饰符/限定符交错;已忽略限定符

在 Microsoft 修饰符之前使用限定符 **`__cdecl`** 是一种过时的做法。

## <a name="example"></a>示例

```cpp
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```
