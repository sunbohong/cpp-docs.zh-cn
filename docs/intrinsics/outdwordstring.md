---
description: 了解详细信息： __outdwordstring
title: __outdwordstring
ms.date: 09/02/2019
f1_keywords:
- __outdwordstring
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
ms.openlocfilehash: 3fbba7dd128666b591305326695e656befd9cada
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180389"
---
# <a name="__outdwordstring"></a>__outdwordstring

**Microsoft 专用**

生成 `rep outsd` 指令，该指令 `Count` 从 `Buffer` 指定的 i/o 端口开始发送双字 `Port` 。

## <a name="syntax"></a>语法

```C
void __outdwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>parameters

*口*\
中要将数据发送到的端口。

*宽限*\
中指向要通过指定端口发送的数据的指针。

*计*\
中要发送的双字的数目。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__outdwordstring`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
