---
description: 了解详细信息： call_as
title: 'call_as (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: de407da1401479327185c6133c625d61e1e221cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247444"
---
# <a name="call_as"></a>call_as

使 [本地](local-cpp.md) 函数能够映射到远程函数，以便在调用远程函数时调用本地函数。

## <a name="syntax"></a>语法

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>parameters

*函数*<br/>
调用远程函数时要调用的本地函数。

## <a name="remarks"></a>备注

**Call_as** c + + 特性具有与 [call_as](/windows/win32/Midl/call-as) MIDL 特性相同的功能。

## <a name="example"></a>示例

下面的代码演示如何使用 **call_as** 将不可远程处理函数 (`f1`) 映射到远程函数 (`Remf1`) ：

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|接口方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[地方](local-cpp.md)
