---
description: 了解更多：编译器错误 C3247
title: 编译器错误 C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 02e8f20f9804067e0179f3b5583d589d16dae302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307173"
---
# <a name="compiler-error-c3247"></a>编译器错误 C3247

“class1”：组件类不能继承自另一个组件类“class2”

[coclass](../../windows/attributes/coclass.md) 特性标记的类不能继承自 `coclass` 特性标记的另一个类。

以下示例生成 C3247：

```cpp
// C3247.cpp
[module(name="MyLib")];
[coclass]
class a {
};

[coclass]
class b : public a {   // C3247
};
int main() {
}
```
