---
title: 'registration_script (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.registration_script
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
ms.openlocfilehash: 8a57f0b3d0925d1e1096a31734fa4c9d666c5743
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846077"
---
# <a name="registration_script"></a>registration_script

执行指定的自定义注册脚本。

## <a name="syntax"></a>语法

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>参数

*script*<br/>
自定义注册脚本的完整路径 ( .rgs) 文件。 如果值为 " **无**" （如 `script = "none"` ），则指示 coclass 没有注册要求。

## <a name="remarks"></a>注解

**Registration_script** c + + 属性执行*脚本*指定的自定义注册脚本。 如果未指定此特性，则使用 (包含用于注册组件) 的信息的标准 .rgs 文件。 有关 .rgs 文件的详细信息，请参阅 [ATL 注册表组件 (注册机构) ](../../atl/atl-registry-component-registrar.md)。

此属性要求 [coclass](coclass.md)、 [progid](progid.md)或 [vi_progid](vi-progid.md) 属性（或隐含这些属性之一的其他属性）也应用于同一个元素。

## <a name="example"></a>示例

下面的代码指定组件具有名为 cpp_attr_ref_registration_script 的注册表脚本。

```cpp
// cpp_attr_ref_registration_script.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="REG")];

[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]
__interface IFace {};

// requires "cpp_attr_ref_registration_script.rgs"
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]
class CMyClass:public IFace {};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**`class`**, **`struct`**|
|**且**|否|
|**必需属性**|以下一项或多项操作： `coclass` 、 `progid` 或 `vi_progid` 。|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[COM 特性](com-attributes.md)<br/>
[类特性](class-attributes.md)<br/>
[rdx](rdx.md)
