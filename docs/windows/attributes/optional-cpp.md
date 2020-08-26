---
title: '可选 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.optional
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
ms.openlocfilehash: 31e2dbac988cdbac8aca2d01a70177825d764a5b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842164"
---
# <a name="optional-c"></a>optional (C++)

为成员函数指定一个可选参数。

## <a name="syntax"></a>语法

```cpp
[optional]
```

## <a name="remarks"></a>备注

**可选**的 c + + 特性与[可选](/windows/win32/Midl/optional)的 MIDL 特性具有相同的功能。

## <a name="example"></a>示例

下面的代码演示如何使用 **可选** ：

```cpp
// cpp_attr_ref_optional.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|接口参数|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[参数属性](parameter-attributes.md)
