---
description: 了解详细信息： __writedr
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 3a52b8985a28268c430cbb1bfb7b2494e9004820
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331875"
---
# <a name="__writedr"></a>__writedr

**Microsoft 专用**

将指定的值写入指定的调试寄存器。

## <a name="syntax"></a>语法

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>parameters

*DebugRegister*\
中标识调试寄存器的从0到7的数字。

*DebugValue*\
中要写入调试寄存器的值。

## <a name="remarks"></a>备注

这些内部函数仅在内核模式下可用，且这些例程只能用作内部函数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__writedr`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
