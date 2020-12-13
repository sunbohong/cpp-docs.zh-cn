---
description: 了解详细信息： _BitScanReverse、_BitScanReverse64
title: _BitScanReverse、_BitScanReverse64
ms.date: 09/02/2019
f1_keywords:
- _BitScanReverse64
- _BitScanReverse_cpp
- _BitScanReverse
- _BitScanReverse64_cpp
helpviewer_keywords:
- bsr instruction
- _BitScanReverse intrinsic
- BitScanReverse intrinsic
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
ms.openlocfilehash: 1a535dcc95f9fbf791de3ecd2c2d54eddcc0399c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337211"
---
# <a name="_bitscanreverse-_bitscanreverse64"></a>_BitScanReverse、_BitScanReverse64

**Microsoft 专用**

从设置位 (1) 的最高有效位 (MSB) 到最低有效位 (LSB) 搜索掩码数据。

## <a name="syntax"></a>语法

```C
unsigned char _BitScanReverse(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanReverse64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

### <a name="parameters"></a>parameters

*编入*\
弄加载时，) 找到第一个设置位 (1。

*掩盖*\
中要搜索的32位或64位值。

## <a name="return-value"></a>返回值

如果设定 `Index`，则为非零，如果未发现设置位，则为 0。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|标头|
|---------------|------------------|------------|
|`_BitScanReverse`|x86、ARM、x64、ARM64|\<intrin.h>|
|`_BitScanReverse64`|ARM64，x64|\<intrin.h>|

## <a name="example"></a>示例

```cpp
// BitScanReverse.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanReverse)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanReverse(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

```Input
12
```

```Output
Enter a positive integer as the mask:
Mask: 12 Index: 3
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
