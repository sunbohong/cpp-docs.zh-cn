---
description: 详细了解 pragma Microsoft c/c + + 中的 fp_contract 指令
title: fp_contract pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragma, fp_contract
- fp_contract pragma
no-loc:
- pragma
ms.openlocfilehash: 3263d1ec9675e0f8a9402ac7da78751b988e7bdf
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713644"
---
# <a name="fp_contract-no-locpragma"></a>`fp_contract` pragma

确定是否发生浮点缩写式。 浮点缩写式是一个指令，如 FMA (的) ，将两个单独的浮点运算合并为一个指令。 使用这些指令可能会影响浮点精度，因为在执行每个运算后，处理器可能仅舍入一次。

## <a name="syntax"></a>语法

> **`#pragma fp_contract (`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>注解

默认情况下， **`fp_contract`** 为 **`on`** 。 这会告知编译器尽可能使用浮点缩写式指令。 设置 **`fp_contract`** 为 **`off`** 以保留单个浮点指令。

有关浮点行为的详细信息，请参阅[ `/fp` (指定浮点行为) ](../build/reference/fp-specify-floating-point-behavior.md)。

其他浮点 pragma 指令包括：

- [`fenv_access`](../preprocessor/fenv-access.md)

- [`float_control`](../preprocessor/float-control.md)

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

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
