---
description: 了解详细信息： _udiv128
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: f88546a179106f4291fcaeb865f1aad9e67c4045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333651"
---
# <a name="_udiv128"></a>_udiv128

`_udiv128`内部函数将128位无符号整数除以64位无符号整数。 返回值保留商，内部函数通过指针参数返回余数。 `_udiv128`**特定于 Microsoft**。

## <a name="syntax"></a>语法

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>parameters

*highDividend* \
中被除数的高64位。

*lowDividend* \
中被除数的低64位。

*divisor* \
中要除以的64位整数。

*剩下* \
弄余数的64位整数位。

## <a name="return-value"></a>返回值

商的64位。

## <a name="remarks"></a>备注

传递 *highDividend* 中的128位的上限64位，以及 *lowDividend* 中的较低64位。 内部函数用 *除数* 除以此值。 它将余数存储在由 *余数* 指向的64位无符号整数中，并返回商的64位。

`_udiv128`从 Visual Studio 2019 RTM 开始可以使用内部函数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|标头|
|---------------|------------------|------------|
|`_udiv128`|X64|\<immintrin.h>|

## <a name="see-also"></a>请参阅

[_div128](div128.md) \
[编译器内部函数](compiler-intrinsics.md)
