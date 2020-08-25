---
title: 'library_block (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 13988abc12eb0b136dfc8d2c0d597005b56f0526
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834111"
---
# <a name="library_block"></a>library_block

将构造置于 IDL 库块内。

## <a name="syntax"></a>语法

```cpp
[library_block]
```

## <a name="remarks"></a>备注

当你将构造放置在库块中时，请确保将其传递到类型库，而不考虑它是否被引用。 默认情况下，仅在库块中放置由 [coclass](coclass.md)、 [调度接口](dispinterface.md)和 [idl_module](idl-module.md) 属性修改的构造。

## <a name="example"></a>示例

在下面的代码中，自定义接口放置在库块内。

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|任何位置|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[编译器特性](compiler-attributes.md)<br/>
[独立属性](stand-alone-attributes.md)
