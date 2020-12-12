---
description: 了解详细信息： __writecr8
title: __writecr8
ms.date: 09/02/2019
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: b9c642d92cd5d5cfb861dbff3d159b5c98a1aa5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331885"
---
# <a name="__writecr8"></a>__writecr8

**Microsoft 专用**

将值写入 `Data` CR8 寄存器。

## <a name="syntax"></a>语法

```C
void writecr8(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>parameters

*数据*\
中要写入到 CR8 寄存器的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__writecr8`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`__writecr8`内部函数仅在内核模式下可用，且例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
