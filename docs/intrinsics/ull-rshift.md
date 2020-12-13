---
description: 了解详细信息： __ull_rshift
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: 5b819e4a1df8db7b7562023c6acc9dbbd94f7f76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333626"
---
# <a name="__ull_rshift"></a>__ull_rshift

**Microsoft 专用**

在 x64 上，将第一个参数指定的64位值向右移动第二个参数指定的位数。

## <a name="syntax"></a>语法

```C
unsigned __int64 __ull_rshift(
   unsigned __int64 mask,
   int nBit
);
```

### <a name="parameters"></a>parameters

*掩盖*\
中要右移的64位整数值。

*nBit*\
中要移位的位数、x86 上的模数32和 x64 上的模数64。

## <a name="return-value"></a>返回值

按位移动的掩码 `nBit` 。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__ull_rshift`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

如果第二个参数大于 x64) 上 x86 (63 上的31个，则在 x64) 上取模 32 (64，以确定要移位的位数。 `ull`名称中的指示 `unsigned long long (unsigned __int64)` 。

## <a name="example"></a>示例

```cpp
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

```Output
1
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshift](../intrinsics/ll-rshift.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
