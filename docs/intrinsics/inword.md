---
description: 了解详细信息： __inword
title: __inword
ms.date: 09/02/2019
f1_keywords:
- __inword_cpp
- __inword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: 8e2d698437cdb27a472872cfe24d7d0ab0a3c768
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167872"
---
# <a name="__inword"></a>__inword

**Microsoft 专用**

使用指令从指定端口读取数据 `in` 。

## <a name="syntax"></a>语法

```C
unsigned short __inword(
   unsigned short Port
);
```

### <a name="parameters"></a>parameters

*口*\
中要从其读取的端口。

## <a name="return-value"></a>返回值

读取的数据的单词。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__inword`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
