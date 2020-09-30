---
title: 编译器错误 C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: c1b8aaddac32af4e0936ce7d45fbc59c3835dda2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501381"
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
