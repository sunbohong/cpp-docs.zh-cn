---
description: 了解详细信息： defaultvtable
title: 'defaultvtable (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 9cabb2e3487788b56a37e7380ef9a9e08cf2bc67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122143"
---
# <a name="defaultvtable"></a>defaultvtable

将接口定义为 COM 对象的默认 vtable 接口。

## <a name="syntax"></a>语法

```cpp
[ defaultvtable(interface) ]
```

### <a name="parameters"></a>parameters

*interface*<br/>
要使 COM 对象具有默认 vtable 的指定接口。

## <a name="remarks"></a>备注

**Defaultvtable** c + + 特性具有与 [defaultvtable](/windows/win32/Midl/defaultvtable) MIDL 特性相同的功能。

## <a name="example"></a>示例

下面的代码演示使用 **defaultvtable** 指定默认接口的类上的属性：

```cpp
// cpp_attr_ref_defaultvtable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI1 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMyI2 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000003")]
__interface IMyI3 {
   HRESULT x();
};

[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),
uuid("00000000-0000-0000-0000-000000000004")]
class CMyC3 : public IMyI3 {};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**`class`**, **`struct`**|
|**且**|否|
|**必需属性**|**coclass**|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[类特性](class-attributes.md)
