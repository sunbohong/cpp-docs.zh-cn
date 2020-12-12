---
description: 了解详细信息： __writecr0
title: __writecr0
ms.date: 09/02/2019
f1_keywords:
- _writecr0
helpviewer_keywords:
- _writecr0 intrinsic
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
ms.openlocfilehash: 9a4cf4f30b5663b875ca27416b698eb8477938d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313094"
---
# <a name="__writecr0"></a>__writecr0

**Microsoft 专用**

将值写入 `Data` CR0 寄存器。

## <a name="syntax"></a>语法

```C
void writecr0(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>parameters

*数据*\
中要写入到 CR0 寄存器的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__writecr0`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此内部函数只在内核模式下可用，例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
