---
description: 了解详细信息： _rotr8、_rotr16
title: _rotr8、_rotr16
ms.date: 09/02/2019
f1_keywords:
- _rotr16
- _rotr8
helpviewer_keywords:
- _rotr8 intrinsic
- _rotr16 intrinsic
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
ms.openlocfilehash: 95908956fe34b654c3602f27b495eb58a0b8f8c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307036"
---
# <a name="_rotr8-_rotr16"></a>_rotr8、_rotr16

**Microsoft 专用**

通过指定的位位置数将输入值向右旋转到最高有效位 (MSB)。

## <a name="syntax"></a>语法

```C
unsigned char _rotr8(
   unsigned char value,
   unsigned char shift
);
unsigned short _rotr16(
   unsigned short value,
   unsigned char shift
);
```

### <a name="parameters"></a>parameters

*负值*\
中要旋转的值。

*格*\
中要旋转的位数。

## <a name="return-value"></a>返回值

旋转的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`_rotr8`|x86、ARM、x64、ARM64|
|`_rotr16`|x86、ARM、x64、ARM64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

与右移位操作不同，执行右旋转时，从低端开始的低序位将移到高位位置。

## <a name="example"></a>示例

```cpp
// rotr.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_rotr8, _rotr16)

int main()
{
    unsigned char c = 'A', c1, c2;

    for (int i = 0; i < 8; i++)
    {
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,
                i, _rotr8(c, i));
    }

    unsigned short s = 0x12;
    int nBit = 10;

    printf_s("Rotating unsigned short 0x%x right by %d bits "
             "gives 0x%x\n",
            s, nBit, _rotr16(s, nBit));
}
```

```Output
Rotating 0x41 right by 0 bits gives 0x41
Rotating 0x41 right by 1 bits gives 0xa0
Rotating 0x41 right by 2 bits gives 0x50
Rotating 0x41 right by 3 bits gives 0x28
Rotating 0x41 right by 4 bits gives 0x14
Rotating 0x41 right by 5 bits gives 0xa
Rotating 0x41 right by 6 bits gives 0x5
Rotating 0x41 right by 7 bits gives 0x82
Rotating unsigned short 0x12 right by 10 bits gives 0x480
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_rotl8，_rotl16](../intrinsics/rotl8-rotl16.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
