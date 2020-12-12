---
description: 了解更多：编译器错误 C3156
title: 编译器错误 C3156
ms.date: 11/04/2016
f1_keywords:
- C3156
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
ms.openlocfilehash: 265e887a7d075267e7a46d47d6bae9621bd83656
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174138"
---
# <a name="compiler-error-c3156"></a>编译器错误 C3156

“class”：不能局部定义托管或 WinRT 类型

函数不能包含托管或 WinRT 类、结构或接口的定义或声明。

## <a name="example"></a>示例

下面的示例生成 C3156。

```cpp
// C3156.cpp
// compile with: /clr /c
void f() {
   ref class X {};   // C3156
   ref class Y;   // C3156
}
```
