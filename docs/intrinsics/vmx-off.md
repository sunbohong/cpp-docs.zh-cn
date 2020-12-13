---
description: 了解详细信息： __vmx_off
title: __vmx_off
ms.date: 09/02/2019
f1_keywords:
- __vmx_off
helpviewer_keywords:
- VMXOFF instruction
- __vmx_off intrinsic
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
ms.openlocfilehash: d36b9079165dd68b207658d6141bdf11bd9747cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333590"
---
# <a name="__vmx_off"></a>__vmx_off

**Microsoft 专用**

在处理器中停用 (.VMX) 操作的虚拟机扩展。

## <a name="syntax"></a>语法

```C
void __vmx_off();
```

## <a name="remarks"></a>备注

`__vmx_off` 函数等同于 `VMXOFF` 计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索文档 "适用于 IA-32 Intel 体系结构的 Intel 虚拟化技术规范" 文档编号 C97063-002。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__vmx_off`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
