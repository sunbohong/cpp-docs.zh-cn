---
description: 了解详细信息： _bittestandreset、_bittestandreset64
title: _bittestandreset、_bittestandreset64
ms.date: 09/02/2019
f1_keywords:
- _bittestandreset64_cpp
- _bittestandreset
- _bittestandreset_cpp
- _bittestandreset64
helpviewer_keywords:
- btr instruction
- _bittestandreset intrinsic
- _bittestandreset64 intrinsic
ms.assetid: 8dad63bb-a051-4cd7-a793-3357537dfeaf
ms.openlocfilehash: 5d0b6133b981a7008bbe4979ee123cebd5ef99fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337169"
---
# <a name="_bittestandreset-_bittestandreset64"></a>_bittestandreset、_bittestandreset64

**Microsoft 专用**

生成指令以检查 `b` 地址的位 `a` ，返回其当前值，然后将位重置为0。

## <a name="syntax"></a>语法

```C
unsigned char _bittestandreset(
   long *a,
   long b
);
unsigned char _bittestandreset64(
   __int64 *a,
   __int64 b
);
```

### <a name="parameters"></a>parameters

*的*\
[in，out]指向要检查的内存的指针。

*b*\
中要测试的位位置。

## <a name="return-value"></a>返回值

指定位置的位。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`_bittestandreset`|x86、ARM、x64、ARM64|
|`_bittestandreset64`|x64、ARM64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

## <a name="example"></a>示例

```cpp
// bittestandreset.cpp
// processor: x86, IPF, x64
#include <stdio.h>
#include <limits.h>
#include <intrin.h>

#pragma intrinsic(_bittestandreset)

// Check the sign bit and reset to 0 (taking the absolute value)
// Returns 0 if the number is positive or zero
// Returns 1 if the number is negative
unsigned char absolute_value(long* p)
{
   const int SIGN_BIT = 31;
   return _bittestandreset(p, SIGN_BIT);
}

int main()
{
    long i = -112;
    unsigned char result;

    // Check the sign bit and reset to 0 (taking the absolute value)

    result = absolute_value(&i);
    if (result == 1)
        printf_s("The number was negative.\n");
}
```

```Output
The number was negative.
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
