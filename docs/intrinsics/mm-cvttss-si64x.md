---
description: 了解详细信息： _mm_cvttss_si64x
title: _mm_cvttss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: a4af7b726d0f15099586bc94348ab4ba7ebf5b8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167625"
---
# <a name="_mm_cvttss_si64x"></a>_mm_cvttss_si64x

**Microsoft 专用**

发出带有截断的 x64 扩展版本的转换 Single-Precision Floating-Point 号到64位整数 (`cvttss2si`) 指令。

## <a name="syntax"></a>语法

```C
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>parameters

*负值*\
中一个 **`__m128`** 包含单精度浮点值的结构。

## <a name="return-value"></a>返回值

第一个浮点值转换为64位整数的结果。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`_mm_cvttss_si64x`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

内部函数与的不同之处在于 `_mm_cvtss_si64x` ，不精确的转换将被截断为零。 因为 **`__m128`** 结构表示 xmm 寄存器，所以生成的指令将数据从一个 xmm 寄存器移到系统内存中。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```cpp
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__m128](../cpp/m128.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
