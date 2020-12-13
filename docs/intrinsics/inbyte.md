---
description: 了解详细信息： __inbyte
title: __inbyte
ms.date: 09/02/2019
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: 77cc1cfb792ffa2f6aef9879820e644372895193
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337019"
---
# <a name="__inbyte"></a>__inbyte

**Microsoft 专用**

生成 `in` 指令，并返回从指定的端口读取的单个字节 `Port` 。

## <a name="syntax"></a>语法

```C
unsigned char __inbyte(
   unsigned short Port
);
```

### <a name="parameters"></a>parameters

*口*\
中要从其读取的端口。

## <a name="return-value"></a>返回值

从指定端口中读取的字节。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__inbyte`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
