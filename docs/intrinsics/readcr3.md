---
description: 了解详细信息： __readcr3
title: __readcr3
ms.date: 09/02/2019
f1_keywords:
- __readcr3
helpviewer_keywords:
- __readcr3 intrinsic
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
ms.openlocfilehash: f430694af6a54dde4839292a10a5267c000ccb86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257337"
---
# <a name="__readcr3"></a>__readcr3

**Microsoft 专用**

读取 CR3 注册并返回其值。

## <a name="syntax"></a>语法

```C
unsigned __int64 __readcr3(void);
```

## <a name="return-value"></a>返回值

CR3 寄存器中的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__readcr3`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

内部函数仅在内核模式下可用，且例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
