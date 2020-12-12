---
description: '了解详细信息：公共 (c + + 特性) '
title: " (c + + COM 特性) 公共 (c + + 属性) "
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: ee6fb641dc122c7d31c25d3433e2a427710ef40a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329653"
---
# <a name="public-c-attributes"></a>public（C++ 特性）

确保 typedef 将进入类型库，即使它未从 .idl 文件中引用。

## <a name="syntax"></a>语法

```cpp
[public]
```

## <a name="remarks"></a>备注

**`public`** C + + 特性具有与 [公共](/windows/win32/Midl/public)MIDL 特性相同的功能。

## <a name="example"></a>示例

下面的代码演示如何使用 **`public`** 特性：

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**`typedef`**|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)
