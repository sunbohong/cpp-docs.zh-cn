---
description: 了解详细信息： _udiv64
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 21f383cd78885ab8d3d8bb66a87623a73b59ff95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333641"
---
# <a name="_udiv64"></a>_udiv64

`_udiv64`内部函数将64位无符号整数除以32位无符号整数。 返回值保留商，内部函数通过指针参数返回余数。 `_udiv64`**特定于 Microsoft**。

## <a name="syntax"></a>语法

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>parameters

*dividend*\
中要相除的64位无符号整数。

*divisor*\
中要作为除数的32位无符号整数。

*剩下*\
弄32位无符号整数余数。

## <a name="return-value"></a>返回值

商的32位。

## <a name="remarks"></a>备注

`_udiv64`内部函数除以 *除数*。 它将余数存储在由 *余数* 指向的32位无符号整数中，并返回商的32位。

`_udiv64`从 Visual Studio 2019 RTM 开始可以使用内部函数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|标头|
|---------------|------------------|------------|
|`_udiv64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>请参阅

[_div64](div64.md) \
[编译器内部函数](compiler-intrinsics.md)
