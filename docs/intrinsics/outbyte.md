---
description: 了解详细信息： __outbyte
title: __outbyte
ms.date: 09/02/2019
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: e062d561719cbcdb32ab980efde9eb568defeadb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222471"
---
# <a name="__outbyte"></a>__outbyte

**Microsoft 专用**

生成 `out` 指令，该指令发送由指定的 i/o 端口指定的1个字节 `Data` `Port` 。

## <a name="syntax"></a>语法

```C
void __outbyte(
   unsigned short Port,
   unsigned char Data
);
```

### <a name="parameters"></a>parameters

*口*\
中要将数据发送到的端口。

*数据*\
中要从指定端口发送的字节。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__outbyte`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
