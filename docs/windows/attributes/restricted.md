---
title: '受限 (c + + COM 特性) '
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: a1f543c4d8edac751195d37414c030dfe2df94fa
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846350"
---
# <a name="restricted"></a>restricted

指定不能任意调用模块、接口或调度接口的成员。

## <a name="syntax"></a>语法

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>参数

*interfaces*<br/>
不能对 COM 对象任意调用的一个或多个接口。 仅当应用于类时，此参数才有效。

## <a name="remarks"></a>注解

**受限制**的 c + + 属性具有与[受限](/windows/win32/Midl/restricted)MIDL 属性相同的功能。

## <a name="example"></a>示例

下面的代码演示如何使用 **受限** 特性：

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|Interface 方法、 **interface**、 **`class`** 、 **`struct`**|
|**且**|否|
|**必需属性**|**coclass**当应用于 **`class`** 或) 时，组件类 (**`struct`**|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[接口特性](interface-attributes.md)<br/>
[方法特性](method-attributes.md)
