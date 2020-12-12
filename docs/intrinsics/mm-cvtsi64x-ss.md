---
description: 了解详细信息： _mm_cvtsi64x_ss
title: _mm_cvtsi64x_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtsi64x_ss
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
ms.openlocfilehash: 81a1af04d4c66cefd9815471baeb3a6095403ddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167716"
---
# <a name="_mm_cvtsi64x_ss"></a>_mm_cvtsi64x_ss

**Microsoft 专用**

生成将64位整数转换为标量 Single-Precision 的 x64 扩展版本 () 指令的 Floating-Point 值 `cvtsi2ss` 。

## <a name="syntax"></a>语法

```C
__m128 _mm_cvtsi64x_ss(
   __m128 a,
   __int64 b
);
```

### <a name="parameters"></a>parameters

*的*\
中一个 **`__m128`** 包含四个单精度浮点值的结构。

*b*\
中要转换为浮点值的64位整数。

## <a name="return-value"></a>返回值

一个 **`__m128`** 结构，其第一个浮点值为转换的结果。 其他三个 *值从中* 复制不变。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`_mm_cvtsi64x_ss`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

**`__m128`** 结构表示一个 xmm 寄存器，因此内部函数允许将值 *b* 从系统内存移到一个 xmm 寄存器中。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```cpp
// _mm_cvtsi64x_ss.cpp
// processor: x64

#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtsi64x_ss)

int main()
{
    __m128 a;
    __int64 b = 54;

    a.m128_f32[0] = 0;
    a.m128_f32[1] = 0;
    a.m128_f32[2] = 0;
    a.m128_f32[3] = 0;
    a = _mm_cvtsi64x_ss(a, b);

    printf_s( "%lf %lf %lf %lf\n",
              a.m128_f32[0], a.m128_f32[1],
              a.m128_f32[2], a.m128_f32[3] );
}
```

```Output
54.000000 0.000000 0.000000 0.000000
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__m128](../cpp/m128.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
