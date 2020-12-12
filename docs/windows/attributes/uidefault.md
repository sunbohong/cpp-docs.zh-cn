---
description: 了解详细信息： uidefault
title: 'uidefault (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uidefault
helpviewer_keywords:
- uidefault attribute
ms.assetid: 200de0e0-2e34-40a2-bae4-8d485a62264d
ms.openlocfilehash: a173679ebdecf31b475fb276741a5ac217cab410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329522"
---
# <a name="uidefault"></a>uidefault

指示类型信息成员是在用户界面中显示的默认成员。

## <a name="syntax"></a>语法

```cpp
[uidefault]
```

## <a name="remarks"></a>备注

**Uidefault** c + + 特性具有与 [uidefault](/windows/win32/Midl/uidefault) MIDL 特性相同的功能。

## <a name="example"></a>示例

下面的代码演示 **uidefault** 的示例：

```cpp
// cpp_attr_ref_uidefault.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom{
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   [uidefault]HRESULT id0([in] long l);
   [uidefault]HRESULT id1([in] long l);

   [uidefault, propget] HRESULT get_y(int *y);
   [uidefault, propput] HRESULT put_y(int y);
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
[方法特性](method-attributes.md)
