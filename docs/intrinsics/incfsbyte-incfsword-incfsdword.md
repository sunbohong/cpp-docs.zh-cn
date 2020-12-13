---
description: 了解详细信息： __incfsbyte、__incfsword __incfsdword
title: __incfsbyte, __incfsword, __incfsdword
ms.date: 09/02/2019
f1_keywords:
- __incfsword
- __incfsbyte_cpp
- __incfsbyte
- __incfsdword
- __incfsword_cpp
- __incfsdword_cpp
helpviewer_keywords:
- __incfsword intrinsic
- __incfsdword intrinsic
- __incfsbyte intrinsic
ms.assetid: 820457fb-e35e-42d3-bcb6-725da3281c64
ms.openlocfilehash: 29d86de51ad282789cb19b72ca953f65af2dc19d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336964"
---
# <a name="__incfsbyte-__incfsword-__incfsdword"></a>__incfsbyte, __incfsword, __incfsdword

**Microsoft 专用**

在相对于段开头的偏移量指定的内存位置，向值添加一个值 `FS` 。

## <a name="syntax"></a>语法

```C
void __incfsbyte(
   unsigned long Offset
);
void __incfsword(
   unsigned long Offset
);
void __incfsdword(
   unsigned long Offset
);
```

### <a name="parameters"></a>parameters

*抵销*\
中与开头之间的偏移量 `FS` 。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__incfsbyte`|x86|
|`__incfsword`|x86|
|`__incfsdword`|x86|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

这些内部函数仅在内核模式下可用，且例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[\__addfsbyte、 \_ _addfsword \_ _addfsdword](../intrinsics/addfsbyte-addfsword-addfsdword.md)\
[\__readfsbyte、 \_ _readfsdword、 \_ _readfsqword \_ _readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)\
[\__writefsbyte、 \_ _writefsdword、 \_ _writefsqword \_ _writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
