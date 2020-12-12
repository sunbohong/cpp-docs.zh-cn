---
description: 了解更多：编译器错误 C3891
title: 编译器错误 C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: df853f3ed0a163b48e75d54561d00298edd215b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144295"
---
# <a name="compiler-error-c3891"></a>编译器错误 C3891

"var"： literal 数据成员不能用作左值

[文本](../../extensions/literal-cpp-component-extensions.md)变量是 const，并且它在声明中初始化后无法更改其值。

下面的示例生成 C3891：

```cpp
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```
