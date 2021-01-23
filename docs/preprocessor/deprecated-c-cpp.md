---
description: 详细了解 pragma Microsoft c/c + + 中不推荐使用的指令
title: 弃用 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragma, deprecated
no-loc:
- pragma
ms.openlocfilehash: 47e049f415b243a4c9959c7adc789f32f91de7ba
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712903"
---
# <a name="deprecated-no-locpragma"></a>`deprecated` pragma

**`deprecated`** pragma 允许你指示在未来版本中可能不再支持某个函数、类型或任何其他标识符，也不应再使用它。

> [!NOTE]
> 有关 c + + 14 属性的信息 `[[deprecated]]` ，以及有关何时使用该属性而不是 Microsoft `__declspec(deprecated)` 修饰符或的指导 **`deprecated`** pragma ，请参阅 [c + + 中的特性](../cpp/attributes.md)。

## <a name="syntax"></a>语法

> **`#pragma deprecated(`***identifier1* [ **`,`** *identifier2* ]**`)`**

## <a name="remarks"></a>注解

当编译器遇到由指定的标识符时 **`deprecated`** pragma ，它会发出编译器警告 [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)。

可以否决宏名称。 将宏名称包含在引号内，否则宏将展开。

由于 **`deprecated`** pragma 适用于所有匹配标识符，并且不考虑签名，因此它不是弃用特定版本重载函数的最佳选项。 引入到作用域中的任何匹配的函数名称都会触发警告。

建议尽可能使用 c + + 14 `[[deprecated]]` 属性，而不是 **`deprecated`** pragma 。 [`__declspec(deprecated)`](../cpp/deprecated-cpp.md)在许多情况下，Microsoft 特定的声明修饰符也是更好的选择 **`deprecated`** pragma 。 `[[deprecated]]`特性和 `__declspec(deprecated)` 修饰符允许您为特定窗体的重载函数指定弃用状态。 仅在对属性或修饰符适用于特定重载函数的引用上显示诊断警告。

## <a name="example"></a>示例

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

以下示例说明如何否决类：

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
