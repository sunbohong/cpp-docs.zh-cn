---
description: 了解更多：编译器错误 C3541
title: 编译器错误 C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: b579697de98556aa99077e43d28e6de828741fb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315161"
---
# <a name="compiler-error-c3541"></a>编译器错误 C3541

"type"：不能将 typeid 应用于包含 "auto" 的类型

[Typeid](../../extensions/typeid-cpp-component-extensions.md)运算符不能应用于所指示的类型，因为它包含 **`auto`** 说明符。

## <a name="example"></a>示例

下面的示例生成 C3541。

```cpp
// C3541.cpp
// Compile with /Zc:auto
#include <typeinfo>
int main() {
    auto x = 123;
    typeid(x);    // OK
    typeid(auto); // C3541
    return 0;
}
```

## <a name="see-also"></a>请参阅

[auto 关键字](../../cpp/auto-cpp.md)<br/>
[/Zc： auto (推导变量类型) ](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
