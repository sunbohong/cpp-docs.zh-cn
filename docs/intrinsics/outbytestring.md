---
description: 了解详细信息： __outbytestring
title: __outbytestring
ms.date: 09/02/2019
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: feadb0b4275e370de88bfc04c8a10f90c41d0844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222419"
---
# <a name="__outbytestring"></a>__outbytestring

**Microsoft 专用**

生成 `rep outsb` 指令，该指令将 `Count` 指向的数据的前个字节发送 `Buffer` 到指定的端口 `Port` 。

## <a name="syntax"></a>语法

```C
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>parameters

*口*\
中要将数据发送到的端口。

*宽限*\
中要从指定端口发送的数据。

*计*\
中要发送的数据的字节数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__outbytestring`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
