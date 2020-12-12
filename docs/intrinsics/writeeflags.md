---
description: 了解详细信息： __writeeflags
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 9c439194782f52b474ec6c6365705ebd8756c6b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331869"
---
# <a name="__writeeflags"></a>__writeeflags

**Microsoft 专用**

将指定的值写入程序状态，并 (EFLAGS) register。

## <a name="syntax"></a>语法

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>parameters

*“值”* \
中要写入到 EFLAGS 寄存器的值。 `Value`对于32位平台，此参数的长度为32位，对于64平台为64位长。

## <a name="remarks"></a>备注

这些例程只能用作内部函数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__writeeflags`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
