---
description: 了解详细信息： __rdtscp
title: __rdtscp
ms.date: 09/02/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: 511d0f1001c218fd838d4bb315fe8c95f10eb3bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257481"
---
# <a name="__rdtscp"></a>__rdtscp

**Microsoft 专用**

生成 `rdtscp` 指令、写入 `TSC_AUX[31:0` ] 到内存，并返回64位时间戳计数器 (`TSC)` 结果。

## <a name="syntax"></a>语法

```C
unsigned __int64 __rdtscp(
   unsigned int * AUX
);
```

### <a name="parameters"></a>parameters

*助*\
弄指向将包含计算机特定寄存器内容的位置的指针 `TSC_AUX[31:0]` 。

## <a name="return-value"></a>返回值

64位无符号整数滴答计数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__rdtscp`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`__rdtscp`内部函数生成 `rdtscp` 指令。 若要确定此指令的硬件支持，请调用 `__cpuid` 内部， `InfoType=0x80000001` 并选中的 bit 27 `CPUInfo[3] (EDX)` 。 如果支持指令，则此位为 1; 否则为0。  如果在不支持指令的硬件上运行使用内部函数的代码 `rdtscp` ，则结果是不可预知的。

此指令将一直等待，直到所有前面的指令都已执行并且以前的所有加载都是全局可见的。 但是，它不是序列化指令。 有关详细信息，请参阅 Intel 和 AMD 手册。

中的值的含义 `TSC_AUX[31:0]` 取决于操作系统。

## <a name="example"></a>示例

```cpp
#include <intrin.h>
#include <stdio.h>
int main()
{
    unsigned __int64 i;
    unsigned int ui;
    i = __rdtscp(&ui);
    printf_s("%I64d ticks\n", i);
    printf_s("TSC_AUX was %x\n", ui);
}
```

```Output
3363423610155519 ticks
TSC_AUX was 0
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__rdtsc](../intrinsics/rdtsc.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
