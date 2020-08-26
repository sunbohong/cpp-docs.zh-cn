---
title: 'importidl (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 8f3c2c5c67ac216d096d1082814c561698f3f732
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842242"
---
# <a name="importidl"></a>importidl

将指定的 .idl 文件插入生成的 .idl 文件。

## <a name="syntax"></a>语法

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>参数

*idl_file*<br/>
标识要与将为应用程序生成的 .idl 文件合并的 .idl 文件的名称。

## <a name="remarks"></a>注解

**Importidl** c + + 特性将该节放置在库块外 (*idl_file*) 到程序生成的 .idl 文件中，并 (将*idl_file*) 到程序生成的 .idl 文件的库部分。

例如，如果想要在生成的 .idl 文件中使用手编码的 .idl 文件，则可能需要使用 **importidl**。

## <a name="example"></a>示例

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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
[独立属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[包括](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
