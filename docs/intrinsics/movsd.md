---
description: 了解详细信息： __movsd
title: __movsd
ms.date: 09/02/2019
f1_keywords:
- __movsd
helpviewer_keywords:
- rep movsd instruction
- __movsd intrinsic
- movsd instruction
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
ms.openlocfilehash: 4a735327253e0a3c605a17119e0821b915fd9394
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133180"
---
# <a name="__movsd"></a>__movsd

**Microsoft 专用**

) 指令生成移动字符串 (`rep movsd` 。

## <a name="syntax"></a>语法

```C
void __movsd(
   unsigned long* Destination,
   unsigned long* Source,
   size_t Count
);
```

### <a name="parameters"></a>parameters

*位置*\
弄操作的目标。

*源程序*\
中操作的源。

*计*\
中要复制的双字的数目。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__movsd`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

结果是将 *源* 指向的第一个计数的第一个 *计数* 复制到 *目标* 字符串。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```cpp
// movsd.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsd)

int main()
{
    unsigned long a1[10];
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,
                            250, 150, 50};
    __movsd(a1, a2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
