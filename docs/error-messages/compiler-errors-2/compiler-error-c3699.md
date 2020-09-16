---
title: 编译器错误 C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: d313168e8033395da1749e000e52421939f77af4
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686647"
---
# <a name="compiler-error-c3699"></a>编译器错误 C3699

"operator"：不能在类型 "type" 上使用此间接寻址

尝试使用上不允许的间接寻址 `type` 。

## <a name="examples"></a>示例

下面的示例生成 C3699。

```cpp
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

普通属性不能具有引用类型。 有关更多信息，请参见 [property](../../extensions/property-cpp-component-extensions.md) 。 下面的示例生成 C3699。

```cpp
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

"指向指针的指针" 语法的等效项是跟踪引用的句柄。 下面的示例生成 C3699。

```cpp
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```
