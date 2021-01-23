---
description: 详细了解 pragma Microsoft c + + 中的托管和非托管指令
title: 托管和非托管 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
helpviewer_keywords:
- managed pragma
- pragma, unmanaged
- pragma, managed
- unmanaged pragma
no-loc:
- pragma
ms.openlocfilehash: a106e9a1370daeedb94bbf5e4d092ae85457a3d2
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713501"
---
# <a name="managed-and-unmanaged-no-locpragma"></a>`managed` 和 `unmanaged` pragma

启用函数级控件以将函数编译为托管或非托管。

## <a name="syntax"></a>语法

> **`#pragma managed`**\
> **`#pragma unmanaged`**\
> **`#pragma managed(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**\
> **`#pragma managed(pop)`**

## <a name="remarks"></a>注解

[`/clr`](../build/reference/clr-common-language-runtime-compilation.md)编译器选项提供用于将函数编译为托管或非托管的模块级控件。

为本机平台编译非托管函数。 此部分程序的执行将由公共语言运行时传递给本机平台。

使用时，函数默认编译为托管 **`/clr`** 。

在应用 **`managed`** 或时 **`unmanaged`** pragma ：

- 添加 pragma 函数前面的，而不是函数体中。

- 添加 pragma after `#include` 语句。 请勿在任何语句前使用它 `#include` 。

**`managed`** **`unmanaged`** pragma 如果 **`/clr`** 编译中未使用，则编译器将忽略和。

当对模板函数进行实例化时， pragma 定义模板时的状态决定了它是托管的还是非托管的。

有关详细信息，请参阅 [混合程序集的初始化](../dotnet/initialization-of-mixed-assemblies.md)。

## <a name="example"></a>示例

```cpp
// pragma_directives_managed_unmanaged.cpp
// compile with: /clr
#include <stdio.h>

// func1 is managed
void func1() {
   System::Console::WriteLine("In managed function.");
}

// #pragma unmanaged
// push managed state on to stack and set unmanaged state
#pragma managed(push, off)

// func2 is unmanaged
void func2() {
   printf("In unmanaged function.\n");
}

// #pragma managed
#pragma managed(pop)

// main is managed
int main() {
   func1();
   func2();
}
```

```Output
In managed function.
In unmanaged function.
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
