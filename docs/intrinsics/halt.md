---
description: 了解详细信息： __halt
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: e38478b14b59c910e6d6ac12f9cb69fa369e3459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336984"
---
# <a name="__halt"></a>__halt

**Microsoft 专用**

暂停微处理器直到已启用的中断、不可屏蔽中断 (NMI) 或重置。

## <a name="syntax"></a>语法

```C
void __halt( void );
```

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__halt`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`__halt`函数等效于 `HLT` 计算机指令，仅在内核模式下可用。 有关详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索文档 "Intel 体系结构软件开发人员手册，第2卷：指令集参考"。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
