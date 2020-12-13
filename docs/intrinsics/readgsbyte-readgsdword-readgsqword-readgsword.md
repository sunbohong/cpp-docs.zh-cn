---
description: 了解详细信息： __readgsbyte、__readgsdword、__readgsqword、__readgsword
title: __readgsbyte、__readgsdword、__readgsqword、__readgsword
ms.date: 09/02/2019
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
ms.openlocfilehash: fb1faf0e785f0d0983d7d3611e68a7515298e61c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340965"
---
# <a name="__readgsbyte-__readgsdword-__readgsqword-__readgsword"></a>__readgsbyte、__readgsdword、__readgsqword、__readgsword

**Microsoft 专用**

从相对于 GS 段开头的偏移量指定的位置读取内存。

## <a name="syntax"></a>语法

```C
unsigned char __readgsbyte(
   unsigned long Offset
);
unsigned short __readgsword(
   unsigned long Offset
);
unsigned long __readgsdword(
   unsigned long Offset
);
unsigned __int64 __readgsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>parameters

*抵销*\
中从开始读取的偏移量 `GS` 。

## <a name="return-value"></a>返回值

字节、字、双字或四声的内存内容 (由位置) 的函数名称指示 `GS:[Offset]` 。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__readgsbyte`|X64|
|`__readgsdword`|X64|
|`__readgsqword`|X64|
|`__readgsword`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

这些例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__writegsbyte、 \_ _writegsdword、 \_ _writegsqword \_ _writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
