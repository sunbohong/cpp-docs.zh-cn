---
description: 了解详细信息： __writecr4
title: __writecr4
ms.date: 09/02/2019
f1_keywords:
- _writecr4
helpviewer_keywords:
- _writecr4 intrinsic
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
ms.openlocfilehash: 711a6dff42f3805886865d09b4638479173bc64e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313081"
---
# <a name="__writecr4"></a>__writecr4

**Microsoft 专用**

将值写入 `Data` CR4 寄存器。

## <a name="syntax"></a>语法

```C
void writecr4(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>parameters

*数据*\
中要写入到 CR4 寄存器的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__writecr4`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此内部函数只在内核模式下可用，例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
