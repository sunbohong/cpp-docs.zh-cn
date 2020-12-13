---
description: 了解详细信息： __svm_vmrun
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: c01716e496513aa11132fdfc95235a39c7277279
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333704"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Microsoft 专用**

开始执行对应于指定虚拟机控制块 (VMCB) 的虚拟机来宾代码。

## <a name="syntax"></a>语法

```C
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>parameters

*VmcbPhysicalAddress*\
中VMCB 的物理地址。

## <a name="remarks"></a>备注

`__svm_vmrun`函数在 VMCB 中使用最少数量的信息来开始执行虚拟机来宾代码。 如果需要更多的信息来处理复杂中断，或切换到另一个来宾，请使用 [__svm_vmsave](../intrinsics/svm-vmsave.md) 或 [__svm_vmload](../intrinsics/svm-vmload.md) 函数。

`__svm_vmrun` 函数等同于 `VMRUN` 计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 站点搜索文档 "AMD64 体系结构程序员手册卷2：系统编程"、文档编号24593、修订版3.11 或更高版本。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__svm_vmrun`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
