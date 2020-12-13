---
description: 了解详细信息： __incgsbyte、__incgsword、__incgsdword、__incgsqword
title: __incgsbyte, __incgsword, __incgsdword, __incgsqword
ms.date: 09/02/2019
f1_keywords:
- __incgsdword
- __incgsqword_cpp
- __incgsword_cpp
- __incgsword
- __incgsbyte
- __incgsbyte_cpp
- __incgsqword
- __incgsdword_cpp
helpviewer_keywords:
- __incgsbyte intrinsic
- __incgsword intrinsic
- __incgsqword intrinsic
- __incgsdword intrinsic
ms.assetid: 06bfdf4f-7643-4fe0-8455-60ce3068073e
ms.openlocfilehash: a19c266c936875765c5681a47845be1a53f18c83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336944"
---
# <a name="__incgsbyte-__incgsword-__incgsdword-__incgsqword"></a>__incgsbyte, __incgsword, __incgsdword, __incgsqword

**Microsoft 专用**

在相对于段开头的偏移量指定的内存位置，向值添加一个值 `GS` 。

## <a name="syntax"></a>语法

```C
void __incgsbyte(
   unsigned long Offset
);
void __incgsword(
   unsigned long Offset
);
void __incgsdword(
   unsigned long Offset
);
void __incgsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>parameters

*抵销*\
中与开头之间的偏移量 `GS` 。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__incgsbyte`|X64|
|`__incgsword`|X64|
|`__incgsdword`|X64|
|`__incgsqword`|X64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

这些例程只能用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[\__addgsbyte、 \_ _addgsword、 \_ _addgsdword \_ _addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)\
[\__readgsbyte、 \_ _readgsdword、 \_ _readgsqword \_ _readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)\
[\__writegsbyte、 \_ _writegsdword、 \_ _writegsqword \_ _writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
