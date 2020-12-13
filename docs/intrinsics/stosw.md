---
description: 了解详细信息： __stosw
title: __stosw
ms.date: 09/02/2019
f1_keywords:
- __stosw
helpviewer_keywords:
- stosw instruction
- __stosw intrinsic
- rep stosw instruction
ms.assetid: 7620fd1d-dba5-40e3-8e07-01aa68895133
ms.openlocfilehash: 2995276fb255858d6c3dd9f438487726e75fdf1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143684"
---
# <a name="__stosw"></a>__stosw

**Microsoft 专用**

)  (生成存储字符串指令 `rep stosw` 。

## <a name="syntax"></a>语法

```C
void __stosw(
   unsigned short* Destination,
   unsigned short Data,
   size_t Count
);
```

### <a name="parameters"></a>parameters

*位置*\
弄操作的目标。

*数据*\
中要存储的数据。

*计*\
中要写入的单词块的长度。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__stosw`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

结果是将单词 *数据* 写入 *目标* 字符串中的 *计数* 词块。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```C
// stosw.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosw)

int main()
{
    unsigned short val = 128;
    unsigned short a[100];
    memset(a, 0, sizeof(a));
    __stosw(a+10, val, 2);
    printf_s("%u %u %u %u", a[9], a[10], a[11], a[12]);
}
```

```Output
0 128 128 0
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
