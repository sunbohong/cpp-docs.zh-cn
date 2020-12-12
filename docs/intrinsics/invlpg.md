---
description: 了解详细信息： __invlpg
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: 16d8f51c8bf36ea94be7b1325ee5bed256c29693
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167898"
---
# <a name="__invlpg"></a>__invlpg

**Microsoft 专用**

生成 x86 `invlpg` 指令，该指令使与按 *地址* 指向的内存关联的页 (TLB) 的转换失效。

## <a name="syntax"></a>语法

```C
void __invlpg(
   void* Address
);
```

### <a name="parameters"></a>parameters

*地址*\
中64位地址。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__invlpg`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

内部函数 `__invlpg` 发出特权指令，仅在具有权限级别 (CPL) 0 的内核模式下可用。

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
