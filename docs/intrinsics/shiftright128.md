---
description: 了解详细信息： __shiftright128
title: __shiftright128
ms.date: 09/02/2019
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: 71f8a0d9b740ebfef5e930715e07d1ec31950269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306971"
---
# <a name="__shiftright128"></a>__shiftright128

**Microsoft 专用**

将 128 位数量（表示为两个 64 位数量 `LowPart` 和 `HighPart`）按 `Shift` 指定的位数右移并返回低 64 位结果。

## <a name="syntax"></a>语法

```C
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>parameters

*LowPart*\
中要移位的128位数量的低64位。

*Largeint.highpart*\
中要移位的128位数量的高64位。

*格*\
中要移位的位数。

## <a name="return-value"></a>返回值

结果的低 64 位。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__shiftright128`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`Shift` 值始终是模 64，如果调用 `__shiftright128(0, 1, 64)`，该函数将向右位移高部分 `0` 位并返回低部分的 `0` 而不是另外预期的 `1`。

## <a name="example"></a>示例

有关示例，请参阅 [__shiftleft128](../intrinsics/shiftleft128.md)。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__shiftleft128](../intrinsics/shiftleft128.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
