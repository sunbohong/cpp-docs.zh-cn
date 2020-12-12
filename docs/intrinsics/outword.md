---
description: 了解详细信息： __outword
title: __outword
ms.date: 09/02/2019
f1_keywords:
- __outword
helpviewer_keywords:
- __outword intrinsic
- out instruction
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
ms.openlocfilehash: 07136a5ae293f7e23a1cf6b0baa2b3a0f0cc54d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257571"
---
# <a name="__outword"></a>__outword

**Microsoft 专用**

生成 `out` 指令，该指令将向外发送由 *端口* 指定的 i/o 端口的单词。

## <a name="syntax"></a>语法

```C
void __outword(
   unsigned short Port,
   unsigned short Data
);
```

### <a name="parameters"></a>parameters

*口*\
中要将数据发送到的端口。

*数据*\
中要发送的数据。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__outword`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
