---
description: 了解详细信息： __svm_vmsave
title: __svm_vmsave
ms.date: 09/02/2019
f1_keywords:
- __svm_vmsave
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
ms.openlocfilehash: 5c0e4eb5f2d4c0f73921572811b070c8f87a2673
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333680"
---
# <a name="__svm_vmsave"></a>__svm_vmsave

**Microsoft 专用**

在 VMCB)  (的指定虚拟机控制块中存储处理器状态的子集。

## <a name="syntax"></a>语法

```C
void __svm_vmsave(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>parameters

*VmcbPhysicalAddress*\
中VMCB 的物理地址。

## <a name="remarks"></a>备注

`__svm_vmsave` 函数等同于 `VMSAVE` 计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) 站点搜索文档 "AMD64 体系结构程序员手册卷2：系统编程"、文档编号24593、修订版3.11 或更高版本。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__svm_vmsave`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
