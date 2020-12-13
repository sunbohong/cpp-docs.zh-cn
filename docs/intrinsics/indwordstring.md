---
description: 了解详细信息： __indwordstring
title: __indwordstring
ms.date: 09/02/2019
f1_keywords:
- __indwordstring
- __indwordstring_cpp
helpviewer_keywords:
- __indwordstring intrinsic
- rep insd instruction
ms.assetid: 96a1cf33-f691-4916-99e4-fa849b61e3a9
ms.openlocfilehash: 18d18a8981a2dd58c0f7bcd366faaf46629647c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336910"
---
# <a name="__indwordstring"></a>__indwordstring

**Microsoft 专用**

使用指令从指定端口读取数据 `rep insd` 。

## <a name="syntax"></a>语法

```C
void __indwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>parameters

*口*\
中要从其读取的端口。

*宽限*\
弄此处写入从端口读取的数据。

*计*\
中要读取的数据的字节数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__indwordstring`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
