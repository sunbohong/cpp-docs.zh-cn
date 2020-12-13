---
description: 了解详细信息： _bittest、_bittest64
title: _bittest、_bittest64
ms.date: 09/02/2019
f1_keywords:
- _bittest64
- _bittest_cpp
- _bittest64_cpp
- _bittest
helpviewer_keywords:
- _bittest intrinsic
- _bittest64 intrinsic
- bt instruction
ms.assetid: 15e62afb-abea-4ee7-a6b1-13efa2034937
ms.openlocfilehash: 50c0f1637fefab9bd39fcbca2cd18571c7769bd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337202"
---
# <a name="_bittest-_bittest64"></a>_bittest、_bittest64

**Microsoft 专用**

生成 `bt` 指令，从而检查地址 `b` 的位置 `a` 中的位，并返回该位的值。

## <a name="syntax"></a>语法

```C
unsigned char _bittest(
   long const *a,
   long b
);
unsigned char _bittest64(
   __int64 const *a,
   __int64 b
);
```

### <a name="parameters"></a>parameters

*的*\
中指向要检查的内存的指针。

*b*\
中要测试的位位置。

### <a name="return-value"></a>返回值

指定位置的位。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|标头|
|---------------|------------------|------------|
|`_bittest`|x86、ARM、x64、ARM64|\<intrin.h>|
|`_bittest64`|ARM64，x64|\<intrin.h>|

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

## <a name="example"></a>示例

```cpp
// bittest.cpp
// processor: x86, ARM, x64

#include <stdio.h>
#include <intrin.h>

long num = 78002;

int main()
{
    unsigned char bits[32];
    long nBit;

    printf_s("Number: %d\n", num);

    for (nBit = 0; nBit < 31; nBit++)
    {
        bits[nBit] = _bittest(&num, nBit);
    }

    printf_s("Binary representation:\n");
    while (nBit--)
    {
        if (bits[nBit])
            printf_s("1");
        else
            printf_s("0");
    }
}
```

```Output
Number: 78002
Binary representation:
0000000000000010011000010110010
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
