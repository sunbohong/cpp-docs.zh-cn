---
title: fenv_access pragma
description: 描述 fenv_access 指令的用法和效果 pragma 。 Fenv_access 指令控制在运行时对浮点环境的访问。
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragma, fenv_access
- fenv_access pragma
no-loc:
- pragma
ms.openlocfilehash: be33bbf9de381850ec78ece204d117ebc537152b
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713657"
---
# <a name="fenv_access-no-locpragma"></a>`fenv_access` pragma

禁用 (**`on`**) 或启用 **`off`** 可能更改浮点环境标记测试和模式更改的 () 优化。

## <a name="syntax"></a>语法

> **`#pragma fenv_access (`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>注解

默认情况下， **`fenv_access`** 为 **`off`** 。 编译器假设您的代码不访问或操作浮点环境。 如果不需要环境访问，编译器可以执行更多操作来优化你的浮点代码。

**`fenv_access`** 如果你的代码测试浮点状态标志、异常或设置控件模式标志，则启用。 编译器禁用浮点优化，因此您的代码可以一致地访问浮点环境。

[/Fp： strict] 命令行选项会自动启用 **`fenv_access`** 。 有关此和其他浮点行为的详细信息，请参阅 [/fp (指定 Floating-Point 行为) ](../build/reference/fp-specify-floating-point-behavior.md)。

**`fenv_access`** pragma 结合使用和其他浮点设置的方式有一些限制：

- **`fenv_access`** 除非启用了精确语义，否则不能启用。 可以通过或 [`float_control`](float-control.md) pragma 使用 [`/fp:precise`](../build/reference/fp-specify-floating-point-behavior.md) 或 [`/fp:strict`](../build/reference/fp-specify-floating-point-behavior.md) 编译器选项来启用精确语义。 **`/fp:precise`** 如果未指定任何其他浮点命令行选项，则编译器将默认为。

- 设置后，不能使用 **`float_control`** 来禁用精确语义 **`fenv_access(on)`** 。

应遵循的优化类型为 **`fenv_access`** ：

- 全局公共子表达式消除

- 代码运动

- 常量折叠

其他浮点 pragma 指令包括：

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>示例

此示例将设置 **`fenv_access`** 为 **`on`** 以设置24位精度的浮点控制寄存器：

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2 /arch:IA32
// processor: x86
#include <stdio.h>
#include <float.h>
#include <errno.h>
#pragma fenv_access (on)

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=9.999999776482582e-03
```

如果 `#pragma fenv_access (on)` 从前面的示例中注释掉，输出将有所不同。 这是因为编译器执行编译时计算，这不会使用控件模式。

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2 /arch:IA32
#include <stdio.h>
#include <float.h>

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=1.000000000000000e-02
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
