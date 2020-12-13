---
description: 了解详细信息： _div64
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 4c9c8f02f7092c12d5734f96346897e2eca9898a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337068"
---
# <a name="_div64"></a>_div64

`_div64`内部函数将64位整数除以32位整数。 返回值保留商，内部函数通过指针参数返回余数。 `_div64`**特定于 Microsoft**。

## <a name="syntax"></a>语法

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>parameters

*dividend* \
中要相除的64位整数。

*divisor* \
中要除以的32位整数。

*剩下* \
弄余数的32位整数位。

## <a name="return-value"></a>返回值

商的32位。

## <a name="remarks"></a>备注

`_div64`内部函数除以 *除数*。 它将余数存储在由 *余数* 指向的32位整数中，并返回商的32位。

`_div64`从 Visual Studio 2019 RTM 开始可以使用内部函数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|标头|
|---------------|------------------|------------|
|`_div64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>请参阅

[_udiv64](udiv64.md) \
[编译器内部函数](compiler-intrinsics.md)
