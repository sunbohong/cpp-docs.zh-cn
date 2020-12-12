---
description: 了解更多：编译器错误 C3816
title: 编译器错误 C3816
ms.date: 11/04/2016
f1_keywords:
- C3816
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
ms.openlocfilehash: b2a4ffc435ad4fc2e0c516d99ade1058799fb4b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180950"
---
# <a name="compiler-error-c3816"></a>编译器错误 C3816

"声明" 以前是用不同的托管或 WinRTmodifier 声明或定义的

前向声明和实际声明要求特性声明中不存在任何冲突或不一致。

下面的示例生成 C3816，并演示如何修复此错误：

```cpp
// C3816a.cpp
// compile with: /clr /c
class C1;
// try the following line instead
// ref class C1;

ref class C1{  // C3816, forward declaration does not use ref
};
```
