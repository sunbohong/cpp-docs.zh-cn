---
description: 了解更多：编译器错误 C3624
title: 编译器错误 C3624
ms.date: 11/04/2016
f1_keywords:
- C3624
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
ms.openlocfilehash: f18b3b7bc013214a1bc9a417e2154cd2d5b4970b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318931"
---
# <a name="compiler-error-c3624"></a>编译器错误 C3624

"type"：使用此类型需要引用程序集 "assembly"

未指定编译你的代码所需的程序集 (引用) ;将程序集传递给 [#using](../../preprocessor/hash-using-directive-cpp.md) 指令。

## <a name="example"></a>示例

下面的示例生成 C3624：

```cpp
// C3624.cpp
// compile with: /clr /c
#using <System.Windows.Forms.dll>

// Uncomment the following 2 lines to resolve.
// #using <System.dll>
// #using <System.Drawing.dll>

using namespace System;

public ref class MyForm : public Windows::Forms::Form {};   // C3624
```
