---
description: 了解更多：编译器错误 C3273
title: 编译器错误 C3273
ms.date: 11/04/2016
f1_keywords:
- C3273
helpviewer_keywords:
- C3273
ms.assetid: 1d2ce9d9-222b-4cab-94e2-d2c1a9f5ebe0
ms.openlocfilehash: 23216089bb6d4a963f04201e742af2f50818efcc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185760"
---
# <a name="compiler-error-c3273"></a>编译器错误 C3273

__finally 不能用于非托管代码中的异常块。

下面的示例生成 C3273：

```cpp
// C3273.cpp
// compile with: /GX
int main()
{
   try
   {
   }
   catch (int)
   {
   }
   __finally   // C3273, remove __finally clause
   {
   }
}
```
