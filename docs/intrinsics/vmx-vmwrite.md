---
description: 了解详细信息： __vmx_vmwrite
title: __vmx_vmwrite
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: d8902d51b05fa96faf22cbb6d80400e1f67c5f3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257298"
---
# <a name="__vmx_vmwrite"></a>__vmx_vmwrite

**Microsoft 专用**

 (VMCS) ，将指定的值写入当前虚拟机控制结构中的指定字段。

## <a name="syntax"></a>语法

```C
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

### <a name="parameters"></a>parameters

*定义域*\
中要写入的 VMCS 字段。

*FieldValue*\
中要写入到 VMCS 字段的值。

## <a name="return-value"></a>返回值

0
操作成功。

2
操作失败，当前 VMCS 的 `VM-instruction error field` 中提供了扩展状态。

pps-2
操作失败，无可用状态。

## <a name="remarks"></a>备注

`__vmx_vmwrite` 函数等同于 `VMWRITE` 计算机指令。 参数的值 `Field` 是一个编码的字段索引，在 Intel 文档中进行了介绍。 有关详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索 "适用于 IA-32 Intel 体系结构的 Intel 虚拟化技术规范" 的附录 C。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmread](../intrinsics/vmx-vmread.md)
