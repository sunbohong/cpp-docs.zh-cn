---
description: 了解详细信息： __movsb
title: __movsb
ms.date: 09/02/2019
f1_keywords:
- __movsb
helpviewer_keywords:
- movsb instruction
- rep movsb instruction
- __movsb intrinsic
ms.assetid: ba5469f6-f797-4cd2-bee8-74c7666c26d4
ms.openlocfilehash: 6e4a9ba7482f7f614b80bd0596111874f0087c86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222445"
---
# <a name="__movsb"></a>__movsb

**Microsoft 专用**

) 指令生成移动字符串 (`rep movsb` 。

## <a name="syntax"></a>语法

```C
void __movsb(
   unsigned char* Destination,
   unsigned const char* Source,
   size_t Count
);
```

### <a name="parameters"></a>parameters

*位置*\
弄指向副本的目标的指针。

*源程序*\
中指向副本的源的指针。

*计*\
中要复制的字节数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__movsb`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

结果是， `Count` 指向的第一个字节将被 `Source` 复制到该 `Destination` 字符串。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```cpp
// movsb.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsb)

int main()
{
    unsigned char s1[100];
    unsigned char s2[100] = "A big black dog.";
    __movsb(s1, s2, 100);

    printf_s("%s %s", s1, s2);
}
```

```Output
A big black dog. A big black dog.
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
