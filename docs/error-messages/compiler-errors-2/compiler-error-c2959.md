---
description: 了解更多：编译器错误 C2959
title: 编译器错误 C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: aa5da1db36ce8544e95ad509402b066e664faf18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210421"
---
# <a name="compiler-error-c2959"></a>编译器错误 C2959

泛型类或函数不能是模板的成员

有关详细信息，请参阅 [Windows 运行时和托管模板](../../extensions/windows-runtime-and-managed-templates-cpp-component-extensions.md) 和 [泛型](../../extensions/generics-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C2959。

```cpp
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```
