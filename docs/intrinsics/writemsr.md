---
description: 了解详细信息： __writemsr
title: __writemsr
ms.date: 09/02/2019
f1_keywords:
- __writemsr
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
ms.openlocfilehash: 0ab7392d9df07a9083ca095bc7002a6bf7d45628
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331852"
---
# <a name="__writemsr"></a>__writemsr

**Microsoft 专用**

) 指令生成写入到模型特定寄存器 (`wrmsr` 。

## <a name="syntax"></a>语法

```C
void __writemsr(
   unsigned long Register,
   unsigned __int64 Value
);
```

### <a name="parameters"></a>parameters

*注册*\
中特定于模型的寄存器。

*“值”* \
中要写入的值。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__writemsr`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此函数只能用于内核模式，此例程仅作为内部函数使用。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
