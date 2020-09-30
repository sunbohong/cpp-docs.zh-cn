---
title: 编译器错误 C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 897defd5643a90234c2ae3b7bb4f58904864e858
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508082"
---
# <a name="compiler-error-c3540"></a>编译器错误 C3540

"type"： sizeof 不能应用于包含 "auto" 的类型

[Sizeof](../../cpp/sizeof-operator.md)运算符不能应用于所指示的类型，因为它包含 **`auto`** 说明符。

## <a name="example"></a>示例

下面的示例生成 C3540。

```cpp
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>请参阅

[auto 关键字](../../cpp/auto-cpp.md)<br/>
[/Zc： auto (推导变量类型) ](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof 运算符](../../cpp/sizeof-operator.md)
