---
description: '了解详细信息：范围 (c + +) '
title: '范围 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.range
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
ms.openlocfilehash: 0c1a45ac1f4e968de52c9ed2bffb89ac2cf5fd04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327356"
---
# <a name="range-c"></a>range (C++)

为其值在运行时设置的参数或字段指定一系列允许的值。

## <a name="syntax"></a>语法

```cpp
[ range(low, high) ]
```

### <a name="parameters"></a>parameters

*低级*<br/>
低范围值。

*严重*<br/>
高范围值。

## <a name="remarks"></a>备注

**范围** c + + 特性具有与 [范围](/windows/win32/Midl/range)MIDL 特性相同的功能。

## <a name="example"></a>示例

```cpp
// cpp_attr_ref_range.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|接口方法，接口参数|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[参数属性](parameter-attributes.md)<br/>
[数据成员特性](data-member-attributes.md)
