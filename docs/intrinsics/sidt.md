---
description: 了解详细信息： __sidt
title: __sidt
ms.date: 09/02/2019
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 075351bc10981dd8453381e9ce9393a046dfd884
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306958"
---
# <a name="__sidt"></a>__sidt

**Microsoft 专用**

存储中断描述符表注册 (IDTR) 在指定内存位置的值。

## <a name="syntax"></a>语法

```C
void __sidt(void * Destination);
```

### <a name="parameters"></a>parameters

*位置*\
中指向存储 IDTR 的内存位置的指针。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__sidt`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`__sidt` 函数等同于 `SIDT` 计算机指令。 有关详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索文档 "Intel 体系结构软件开发人员手册，第2卷：指令集参考"。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__lidt](../intrinsics/lidt.md)
