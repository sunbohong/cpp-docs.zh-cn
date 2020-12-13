---
description: 了解详细信息： __indword
title: __indword
ms.date: 09/02/2019
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
ms.openlocfilehash: bd637027ee930b551f08508874554e2b19f22461
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336930"
---
# <a name="__indword"></a>__indword

**Microsoft 专用**

使用指令从指定端口读取一个双字数据 `in` 。

## <a name="syntax"></a>语法

```C
unsigned long __indword(
   unsigned short Port
);
```

### <a name="parameters"></a>parameters

*口*\
中要从其读取的端口。

## <a name="return-value"></a>返回值

从端口读取的字词。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__indword`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
