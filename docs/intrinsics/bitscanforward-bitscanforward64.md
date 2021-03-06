---
description: 了解详细信息： _BitScanForward、_BitScanForward64
title: _BitScanForward、_BitScanForward64
ms.date: 09/02/2019
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 182f22b5350fcad7c3da9a0d6f6df36c0871a3e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337222"
---
# <a name="_bitscanforward-_bitscanforward64"></a>_BitScanForward、_BitScanForward64

**Microsoft 专用**

从设置位 (1) 的最低有效位 (LSB) 到最高有效位 (MSB) 搜索掩码数据。

## <a name="syntax"></a>语法

```C
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
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

如果掩码为零，则为 0；否则为非零值。

## <a name="remarks"></a>备注

如果找到一个设置位，则将在第一个参数中返回已找到的第一个设置位的位位置。 如果没有发现任何设置位，则返回 0；否则返回 1。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`_BitScanForward`|x86、ARM、x64、ARM64|
|`_BitScanForward64`|ARM64，x64|

**头文件** \<intrin.h>

## <a name="example"></a>示例

```cpp
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
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
Mask: 12 Index: 2
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
