---
description: 了解详细信息： __svm_invlpga
title: __svm_invlpga
ms.date: 09/02/2019
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: dc976f535381fcfdfec0da5c1a280c4df281c114
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314745"
---
# <a name="__svm_invlpga"></a>__svm_invlpga

**Microsoft 专用**

使计算机的翻译外观缓冲区中的地址映射条目失效。 参数指定要使其无效的页的虚拟地址和地址空间标识符。

## <a name="syntax"></a>语法

```C
void __svm_invlpga(void *Vaddr, int as_id);
```

### <a name="parameters"></a>parameters

*Vaddr*\
中要使其无效的页的虚拟地址。

*as_id*\
中要使其无效的页的地址空间标识符 (ASID) 。

## <a name="remarks"></a>备注

`__svm_invlpga` 函数等同于 `INVLPGA` 计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 站点搜索文档 "AMD64 体系结构程序员手册卷2：系统编程，文档编号24593，修订版 3.11"。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__svm_invlpga`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
