---
description: 了解详细信息： __vmx_vmclear
title: __vmx_vmclear
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 2eec5c1189c6a798246a6dabfc731fb0166bc14a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333558"
---
# <a name="__vmx_vmclear"></a>__vmx_vmclear

**Microsoft 专用**

 (VMCS) 初始化指定的虚拟机控制结构，并将其启动状态设置为 `Clear` 。

## <a name="syntax"></a>语法

```C
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>parameters

*VmcsPhysicalAddress*\
中指向64位内存位置的指针，该内存位置包含要清除的 VMCS 的物理地址。

## <a name="return-value"></a>返回值

|值|含义|
|-----------|-------------|
|0|操作成功。|
|1|操作失败，当前 VMCS 的 `VM-instruction error field` 中提供了扩展状态。|
|2|操作失败，无可用状态。|

## <a name="remarks"></a>备注

应用程序可以使用 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 或 [__VMX_VMRESUME](../intrinsics/vmx-vmresume.md) 函数执行 VM 输入操作。 [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)函数只能与启动状态为的 VMCS 一起使用 `Clear` ，并且[__vmx_vmresume](../intrinsics/vmx-vmresume.md)函数只能与启动状态为的 VMCS 一起使用 `Launched` 。 因此，使用 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 函数将 VMCS 的启动状态设置为 `Clear` 。 对第一个 VM 输入操作使用 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 函数，为后续 vm 输入操作使用 [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 函数。

`__vmx_vmclear` 函数等同于 `VMCLEAR` 计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索文档 "适用于 IA-32 Intel 体系结构的 Intel 虚拟化技术规范" 文档编号 C97063-002。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__vmx_vmclear`|X64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)
