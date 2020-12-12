---
description: 了解更多：编译器错误 C3628
title: 编译器错误 C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: ed0c434a40e6c513580e37b5fb2fc9f44b1dc5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144399"
---
# <a name="compiler-error-c3628"></a>编译器错误 C3628

"基类"：托管或 WinRTclasses 仅支持公共继承

尝试使用托管或 WinRT 类作为 [私有](../../cpp/private-cpp.md) 或 [受保护](../../cpp/protected-cpp.md) 的基类。 托管类或 WinRT 类只能用作具有 [公共](../../cpp/public-cpp.md) 访问权限的基类。

下面的示例生成 C3628，并演示如何修复此错误：

```cpp
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
