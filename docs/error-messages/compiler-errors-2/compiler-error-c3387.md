---
description: 了解更多：编译器错误 C3387
title: 编译器错误 C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: febd47004026a7e22ca576c153ee8cf1506c3e1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285547"
---
# <a name="compiler-error-c3387"></a>编译器错误 C3387

"member"： __declspec (dllexport) / \_ _declspec (dllimport) 无法应用于托管或 WinRT 类型的成员

`dllimport`和 [dllexport](../../cpp/dllexport-dllimport.md) **`__declspec`** 修饰符在托管或 Windows 运行时类型的成员上无效。

下面的示例将生成 C3387，并演示如何修复此错误：

```cpp
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```
