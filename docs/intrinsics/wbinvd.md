---
description: 了解详细信息： __wbinvd
title: __wbinvd
ms.date: 09/02/2019
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: b40e1b618e49ab317a7b9cdeea647bcd58df7912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257259"
---
# <a name="__wbinvd"></a>__wbinvd

**Microsoft 专用**

生成写回，并使缓存 (`wbinvd`) 指令无效。

## <a name="syntax"></a>语法

```C
void __wbinvd(void);
```

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__wbinvd`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此函数仅在具有权限级别 (CPL) 为0的内核模式下可用，且例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
