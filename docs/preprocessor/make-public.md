---
description: 详细了解 pragma Microsoft c/c + + 中的 make_public 指令
title: make_public pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragma, make_public
- make_public pragma
no-loc:
- pragma
ms.openlocfilehash: 4bc3370ac0901ff9a0656de5657f9c9f557e1dff
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713514"
---
# <a name="make_public-no-locpragma"></a>`make_public` pragma

指示本机类型应具有公共程序集可访问性。

## <a name="syntax"></a>语法

> **`#pragma make_public(`***类型***`)`**

### <a name="parameters"></a>Parameters

*type*\
要具有公共程序集可访问性的类型的名称。

## <a name="remarks"></a>注解

**`make_public`** 如果要引用的本机类型来自无法更改的标头文件，则此方法非常有用。 如果要在具有公共程序集可见性的类型中的公共函数签名中使用本机类型，则本机类型还必须具有公共程序集可访问性，否则编译器将发出警告。

**`make_public`** 必须在全局范围内指定。 它仅从其声明到源代码文件末尾的点起生效。

本机类型可以隐式或显式私有。 有关详细信息，请参阅 [类型可见性](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)。

## <a name="examples"></a>示例

下面的示例是包含两个本机结构的定义的头文件的内容。

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

下面的代码示例使用头文件。 其中显示，除非你使用将本机结构显式标记为公共，否则， **`make_public`** 当你尝试在公共托管类型中的公共函数签名中使用本机结构时，编译器将生成警告。

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
