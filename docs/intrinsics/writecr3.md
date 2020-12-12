---
description: 了解详细信息： __writecr3
title: __writecr3
ms.date: 09/02/2019
f1_keywords:
- _writecr3
helpviewer_keywords:
- _writecr3 intrinsic
ms.assetid: 959d49fa-69d5-47cf-88d2-7688367fe38f
ms.openlocfilehash: fa4555b2fe4a67dcb3669f8ae20ea0e2d76c8984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313107"
---
# <a name="__writecr3"></a>__writecr3

**Microsoft 专用**

将值写入 `Data` CR3 寄存器。

## <a name="syntax"></a>语法

```C
void writecr3(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>parameters

*数据*\
中要写入到 CR3 寄存器的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__writecr3`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此内部函数只在内核模式下可用，例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
