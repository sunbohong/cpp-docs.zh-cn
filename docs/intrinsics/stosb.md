---
description: 了解详细信息： __stosb
title: __stosb
ms.date: 09/02/2019
f1_keywords:
- __stosb
helpviewer_keywords:
- rep stosb instruction
- __stosb intrinsic
- stosb instruction
ms.assetid: 634589ed-2da3-439b-a381-a214d89bf10c
ms.openlocfilehash: 8fa8b506b1b4a15738d2eaebeeaad4b547b2f02e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143723"
---
# <a name="__stosb"></a>__stosb

**Microsoft 专用**

)  (生成存储字符串指令 `rep stosb` 。

## <a name="syntax"></a>语法

```C
void __stosb(
   unsigned char* Destination,
   unsigned char Data,
   size_t Count
);
```

### <a name="parameters"></a>parameters

*位置*\
弄操作的目标。

*数据*\
中要存储的数据。

*计*\
中要写入的字节块的长度。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__stosb`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

结果是字符 *数据* 写入 *目标* 字符串中的 *计数* 字节块。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```C
// stosb.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosb)

int main()
{
    unsigned char c = 0x40; /* '@' character */
    unsigned char s[] = "*********************************";

    printf_s("%s\n", s);
    __stosb((unsigned char*)s+1, c, 6);
    printf_s("%s\n", s);

}
```

```Output
*********************************
*@@@@@@**************************
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
