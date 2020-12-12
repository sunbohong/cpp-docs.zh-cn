---
description: 了解详细信息： __lidt
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 9b9f4bc51bab07a578671932c16548a0a49d155b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167768"
---
# <a name="__lidt"></a>__lidt

**Microsoft 专用**

加载中断描述符表注册 (IDTR) ，其值在指定的内存位置。

## <a name="syntax"></a>语法

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>parameters

*源程序*\
中指向要复制到 IDTR 的值的指针。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__lidt`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`__lidt`函数等效于 `LIDT` 计算机指令，仅在内核模式下可用。 有关详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索文档 "Intel 体系结构软件开发人员手册，第2卷：指令集参考"。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
