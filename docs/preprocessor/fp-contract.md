---
description: 了解详细信息： fp_contract 杂注
title: fp_contract 杂注
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
ms.openlocfilehash: cefcf0519f08b3fd68a0f8b464938ea7cdbda6d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261172"
---
# <a name="fp_contract-pragma"></a>fp_contract 杂注

确定是否发生浮点缩写式。 浮点缩写式是一个指令，如 FMA (的) ，将两个单独的浮点运算合并为一个指令。 使用这些指令可能会影响浮点精度，因为在执行每个运算后，处理器可能仅舍入一次。

## <a name="syntax"></a>语法

> **#pragma fp_contract (** { **on**  |  **off** } **)**

## <a name="remarks"></a>备注

默认情况下， **fp_contract** 为 **on**。 这会告知编译器尽可能使用浮点缩写式指令。 将 **fp_contract** 设置为 **off** ，以保留单个浮点指令。

有关浮点行为的详细信息，请参阅 [/fp (指定 Floating-Point 行为) ](../build/reference/fp-specify-floating-point-behavior.md)。

其他浮点杂注包括：

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>示例

此示例生成的代码不使用带外乘添加指令，即使它在目标处理器上可用也是如此。 如果注释掉 `#pragma fp_contract (off)` ，则生成的代码可能会使用带外乘添加指令（如果可用）。

```cpp
// pragma_directive_fp_contract.cpp
// on x86 and x64 compile with: /O2 /fp:fast /arch:AVX2
// other platforms compile with: /O2

#include <stdio.h>

// remove the following line to enable FP contractions
#pragma fp_contract (off)

int main() {
   double z, b, t;

   for (int i = 0; i < 10; i++) {
      b = i * 5.5;
      t = i * 56.025;

      z = t * i + b;
      printf("out = %.15e\n", z);
   }
}
```

```Output
out = 0.000000000000000e+00
out = 6.152500000000000e+01
out = 2.351000000000000e+02
out = 5.207249999999999e+02
out = 9.184000000000000e+02
out = 1.428125000000000e+03
out = 2.049900000000000e+03
out = 2.783725000000000e+03
out = 3.629600000000000e+03
out = 4.587525000000000e+03
```

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
