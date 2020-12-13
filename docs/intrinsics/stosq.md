---
description: 了解详细信息： __stosq
title: __stosq
ms.date: 09/02/2019
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: 5fce587c163da18679750c20ec697c489ecf5d90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143697"
---
# <a name="__stosq"></a>__stosq

**Microsoft 专用**

)  (生成存储字符串指令 `rep stosq` 。

## <a name="syntax"></a>语法

```C
void __stosb(
   unsigned __int64* Destination,
   unsigned __int64 Data,
   size_t Count
);
```

### <a name="parameters"></a>parameters

*位置*\
弄操作的目标。

*数据*\
中要存储的数据。

*计*\
中要写入的 quadwords 块的长度。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__stosq`|AMD64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

结果就是，将四 quadwords *数据* 写入 *目标* 字符串中的 *计数* 块。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```C
// stosq.c
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosq)

int main()
{
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;
   unsigned __int64 a[10];
   memset(a, 0, sizeof(a));
   __stosq(a+1, val, 2);
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff ffffffffffff 0
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
