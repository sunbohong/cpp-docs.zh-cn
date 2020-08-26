---
title: 'ms_union (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ms_union
helpviewer_keywords:
- ms_union attribute
ms.assetid: bb548689-6962-457e-af56-8ffdf68987eb
ms.openlocfilehash: ae99a996cd7969da27f38ad3532f0472f389ee3d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838836"
---
# <a name="ms_union"></a>ms_union

控制 nonencapsulated 联合的网络数据表示形式的对齐方式。

## <a name="syntax"></a>语法

```cpp
[ms_union]
```

## <a name="remarks"></a>备注

**Ms_union** c + + 特性具有与[ms_union](/windows/win32/Midl/ms-union-attrib) MIDL 特性相同的功能。

## <a name="example"></a>示例

下面的代码演示 **ms_union**的位置：

```cpp
// cpp_attr_ref_ms_union.cpp
// compile with: /LD
#include <unknwn.h>
[object, ms_union, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl {
   HRESULT DisplayString([in, string] char * p1);
};

[export, switch_type(short)] union _WILLIE_UNION_TYPE  {
   [case(24)]
      float fMays;
   [case(25)]
      double dMcCovey;
   [default]
      int x;
};

[public] typedef _WILLIE_UNION_TYPE WILLIE_UNION_TYPE;

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|Nonencapsulated 联合|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|`dispinterface`|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)
