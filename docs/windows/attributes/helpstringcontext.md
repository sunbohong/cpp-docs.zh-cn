---
title: 'helpstringcontext (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: 9e089c210ad52d8ee07291c174a151f5077ae074
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830977"
---
# <a name="helpstringcontext"></a>helpstringcontext

指定 .hlp 或 .chm 文件中帮助主题的 ID。

## <a name="syntax"></a>语法

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>参数

*contextID*<br/>
**帮助**文件中的32位帮助上下文标识符。

## <a name="remarks"></a>注解

**Helpstringcontext** c + + 特性具有与[helpstringcontext](/windows/win32/Midl/helpstringcontext) ODL 特性相同的功能。

## <a name="example"></a>示例

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object, helpstring("help string"), helpstringcontext(1), uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**`class`**、 **接口**、接口方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[接口特性](interface-attributes.md)<br/>
[类特性](class-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[模块](module-cpp.md)
