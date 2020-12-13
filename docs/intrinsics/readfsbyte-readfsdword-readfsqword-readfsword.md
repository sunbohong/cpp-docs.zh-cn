---
description: 了解详细信息： __readfsbyte、__readfsdword、__readfsqword、__readfsword
title: __readfsbyte、__readfsdword、__readfsqword、__readfsword
ms.date: 09/02/2019
f1_keywords:
- __readfsword
- __readfsdword
- __readfsbyte
- __readfsqword
helpviewer_keywords:
- __readfsword intrinsic
- readfsword intrinsic
- __readfsdword intrinsic
- readfsbyte intrinsic
- __readfsbyte intrinsic
- readfsdword intrinsic
- readfsqword intrinsic
- __readfsqword intrinsic
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
ms.openlocfilehash: 2b733ced12045253c78e823379c10a5e70f65143
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340978"
---
# <a name="__readfsbyte-__readfsdword-__readfsqword-__readfsword"></a>__readfsbyte、__readfsdword、__readfsqword、__readfsword

**Microsoft 专用**

从相对于 FS 段开头的偏移量指定的位置读取内存。

## <a name="syntax"></a>语法

```C
unsigned char __readfsbyte(
   unsigned long Offset
);
unsigned short __readfsword(
   unsigned long Offset
);
unsigned long __readfsdword(
   unsigned long Offset
);
unsigned __int64 __readfsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>parameters

*抵销*\
中从开始读取的偏移量 `FS` 。

## <a name="return-value"></a>返回值

字节、字、双字或四长四 (的内存内容由位置) 名为的函数的名称指示 `FS:[Offset]` 。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__readfsbyte`|x86|
|`__readfsdword`|x86|
|`__readfsqword`|x86|
|`__readfsword`|x86|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

这些例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__writefsbyte、 \_ _writefsdword、 \_ _writefsqword \_ _writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
