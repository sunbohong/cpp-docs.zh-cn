---
description: 了解更多：编译器错误 C3540
title: 编译器错误 C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 85106061b2631d3a392b05a50c49f24566cdd4cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112448"
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
