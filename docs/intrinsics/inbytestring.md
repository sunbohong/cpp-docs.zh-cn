---
description: 了解详细信息： __inbytestring
title: __inbytestring
ms.date: 09/02/2019
f1_keywords:
- __inbytestring
- __inbytestring_cpp
helpviewer_keywords:
- rep insb instruction
- __inbytestring intrinsic
ms.assetid: fe549556-e7a3-4af3-8ebf-8a7dc3cb233b
ms.openlocfilehash: cf529fe0049a9bdd22341fcf492b40e2e92cec48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336949"
---
# <a name="__inbytestring"></a>__inbytestring

**Microsoft 专用**

使用指令从指定端口读取数据 `rep insb` 。

## <a name="syntax"></a>语法

```C
void __inbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>parameters

*口*\
中要从其读取的端口。

*宽限*\
弄此处写入从端口读取的数据。

*计*\
中要读取的数据的字节数。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__inbytestring`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
