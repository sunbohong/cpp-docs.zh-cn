---
description: 了解详细信息： __readpmc
title: __readpmc
ms.date: 09/02/2019
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: ceff8522d4895f69a47cf429e59d267c671e3a66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294126"
---
# <a name="__readpmc"></a>__readpmc

**Microsoft 专用**

生成 `rdpmc` 指令，该指令读取由 *counter* 指定的性能监视计数器。

## <a name="syntax"></a>语法

```C
unsigned __int64 __readpmc(
   unsigned long counter
);
```

### <a name="parameters"></a>parameters

*对抗*\
中要读取的性能计数器。

## <a name="return-value"></a>返回值

指定的性能计数器的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__readpmc`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

内部函数仅在内核模式下可用，且例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
