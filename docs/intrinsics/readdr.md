---
description: 了解详细信息： __readdr
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: b3b5952d940db91b278344ab45edb3e8b914c094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341004"
---
# <a name="__readdr"></a>__readdr

**Microsoft 专用**

读取指定的调试寄存器的值。

## <a name="syntax"></a>语法

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>parameters

*DebugRegister*\
中用于标识调试寄存器的从0到7的常数。

## <a name="return-value"></a>返回值

指定的调试寄存器的值。

## <a name="remarks"></a>备注

这些内部函数仅在内核模式下可用，且这些例程只能用作内部函数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__readdr`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
