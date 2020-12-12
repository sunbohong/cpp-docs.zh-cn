---
description: 了解详细信息： _ReadBarrier
title: _ReadBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: 94ade7c8f602cf279ac75a5f0a56387c344d0fb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257482"
---
# <a name="_readbarrier"></a>_ReadBarrier

**Microsoft 专用**

限制可重新排列调用点上的内存访问操作的编译器优化。

> [!CAUTION]
> 已全部弃用且不应使用 `_ReadBarrier`、`_WriteBarrier` 和 `_ReadWriteBarrier` 编译器内部函数和 `MemoryBarrier` 宏。 对于线程间的通信，请使用[c + + 标准库](../standard-library/cpp-standard-library-reference.md)中定义的机制，例如[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)和[std：：原子 \<T> ](../standard-library/atomic.md) 。 对于硬件访问，请将 [/volatile： iso](../build/reference/volatile-volatile-keyword-interpretation.md) 编译器选项与 [volatile](../cpp/volatile-cpp.md) 关键字一起使用。

## <a name="syntax"></a>语法

```C
void _ReadBarrier(void);
```

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`_ReadBarrier`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`_ReadBarrier` 内部函数将限制可删除或重新排列调用点上的内存访问操作的编译器优化。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[关键字](../cpp/keywords-cpp.md)
