---
description: 了解详细信息： __nop
title: __nop
ms.date: 09/02/2019
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 55759e8324511b6ddaa2774bdfdc3554c0032c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118922"
---
# <a name="__nop"></a>__nop

**Microsoft 专用**

生成不执行任何操作的特定于平台的计算机代码。

## <a name="syntax"></a>语法

```C
void __nop();
```

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__nop`|x86、ARM、x64、ARM64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="remarks"></a>备注

`__nop` 函数等同于 `NOP` 计算机指令。 有关 x86 和 x64 的详细信息，请在 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 站点搜索文档 "Intel 体系结构软件开发人员手册，第2卷：指令集参考"。

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__noop](../intrinsics/noop.md)
