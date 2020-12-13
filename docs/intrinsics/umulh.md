---
description: 了解详细信息： __umulh
title: __umulh
ms.date: 09/02/2019
f1_keywords:
- __umulh
helpviewer_keywords:
- __umulh intrinsic
ms.assetid: d241b53a-e6f7-4af1-9f6e-84e149158f03
ms.openlocfilehash: 1d727d72155bdfb5cd5da1ee56c514af26b5ae89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333608"
---
# <a name="__umulh"></a>__umulh

**Microsoft 专用**

返回两个 64 位无符号整数的产品的高 64 位。

## <a name="syntax"></a>语法

```C
unsigned __int64 __umulh(
   unsigned __int64 a,
   unsigned __int64 b
);
```

### <a name="parameters"></a>parameters

*的*\
[输入] 要相乘的第一个数字。

*b*\
[输入] 要相乘的第二个数字。

## <a name="return-value"></a>返回值

128 位乘法运算结果的高 64 位。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__umulh`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

这些例程只能用作内部函数。

## <a name="example"></a>示例

```cpp
// umulh.cpp
// processor: X64
#include <cstdio>
#include <intrin.h>

int main()
{
    unsigned __int64 i = 0x10;
    unsigned __int64 j = 0xFEDCBA9876543210;
    unsigned __int64 k = i * j; // k has the low 64 bits
                                // of the product.
    unsigned __int64 result;
    result = __umulh(i, j); // result has the high 64 bits
                            // of the product.
    printf_s("0x%I64x * 0x%I64x = 0x%I64x%I64x \n", i, j, result, k);
    return 0;
}
```

```Output
0x10 * 0xfedcba9876543210 = 0xfedcba98765432100
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
