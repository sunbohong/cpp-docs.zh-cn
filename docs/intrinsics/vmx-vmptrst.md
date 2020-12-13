---
description: 了解详细信息： __vmx_vmptrst
title: __vmx_vmptrst
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 216da453acf5c04e4189271185567841327571ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333524"
---
# <a name="__vmx_vmptrst"></a>__vmx_vmptrst

**Microsoft 专用**

将指针存储到当前虚拟机控制结构 () 指定地址处的 VMCS。

## <a name="syntax"></a>语法

```C
void __vmx_vmptrst(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>parameters

*VmcsPhysicalAddress*\
中当前 VMCS 指针存储到的地址。

## <a name="remarks"></a>备注

VMCS 指针是一个64位的物理地址。

`__vmx_vmptrst` 函数等同于 `VMPTRST` 计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索文档 "适用于 IA-32 Intel 体系结构的 Intel 虚拟化技术规范" 文档编号 C97063-002。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__vmx_vmptrst`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)
