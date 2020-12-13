---
description: 了解详细信息： __svm_vmload
title: __svm_vmload
ms.date: 09/02/2019
f1_keywords:
- __svm_vmload
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
ms.openlocfilehash: 975f6aed50007b0b184bbab2b9b48790e5e20616
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333708"
---
# <a name="__svm_vmload"></a>__svm_vmload

**Microsoft 专用**

从指定的虚拟机控制块加载部分处理器状态 (VMCB) 。

## <a name="syntax"></a>语法

```C
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>parameters

*VmcbPhysicalAddress*\
中VMCB 的物理地址。

## <a name="remarks"></a>备注

`__svm_vmload` 函数等同于 `VMLOAD` 计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 站点搜索文档 "AMD64 体系结构程序员手册卷2：系统编程，文档编号24593，修订版 3.11"。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__svm_vmload`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)
