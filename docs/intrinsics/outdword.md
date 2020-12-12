---
description: 了解详细信息： __outdword
title: __outdword
ms.date: 09/02/2019
f1_keywords:
- __outdword
helpviewer_keywords:
- out instruction
- outdword instruction
- __outdword intrinsic
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
ms.openlocfilehash: e1d5f79231675ca64a340138ebda24a56e485ab1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222341"
---
# <a name="__outdword"></a>__outdword

**Microsoft 专用**

生成 `out` 指令，以将双字 *数据* 输出到端口 *端口*。

## <a name="syntax"></a>语法

```C
void __outdword(
   unsigned short Port,
   unsigned long Data
);
```

### <a name="parameters"></a>parameters

*口*\
中要将数据发送到的端口。

*数据*\
中要发送的双字。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__outdword`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
