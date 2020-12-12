---
description: 了解详细信息： __rdtsc
title: __rdtsc
ms.date: 09/02/2019
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 930c8fbd0ae762c8674a85e379899bc4fe4d3394
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257506"
---
# <a name="__rdtsc"></a>__rdtsc

**Microsoft 专用**

生成 `rdtsc` 指令，该指令返回处理器时间戳。 处理器时间戳记录自上次重置以来的时钟周期数。

## <a name="syntax"></a>语法

```C
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>返回值

表示滴答计数的64位无符号整数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__rdtsc`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅作为内部函数提供。

在更高版本的硬件中，对 TSC 值的解释不同于早期版本的 x64。 有关详细信息，请参阅硬件手册。

## <a name="example"></a>示例

```cpp
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
