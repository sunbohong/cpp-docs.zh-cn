---
description: 了解详细信息： __readcr8
title: __readcr8
ms.date: 09/02/2019
f1_keywords:
- __readcr8
helpviewer_keywords:
- __readcr8 intrinsic
ms.assetid: fce16953-87ff-4fbe-8081-7962b97ae46c
ms.openlocfilehash: 1961f00575956c8377131cd0871e59f79db5dc1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341017"
---
# <a name="__readcr8"></a>__readcr8

**Microsoft 专用**

读取 CR8 注册并返回其值。

## <a name="syntax"></a>语法

```C
unsigned __int64 __readcr8(void);
```

## <a name="return-value"></a>返回值

CR8 寄存器中的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__readcr8`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

内部函数仅在内核模式下可用，且例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
