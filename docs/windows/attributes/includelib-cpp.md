---
description: '了解详细信息： includelib (c + +) '
title: 'includelib (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 9a7565a931a865b69f0da95da9e92481b27de3b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321345"
---
# <a name="includelib-c"></a>includelib (C++)

导致在生成的 .idl 文件中包含 .idl 或 .h 文件。

## <a name="syntax"></a>语法

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>parameters

*名称 .idl*<br/>
要包含在生成的 .idl 文件中的 .idl 文件的名称。

## <a name="remarks"></a>备注

**Includelib** c + + 特性会导致在生成的 .idl 文件中包含一个 .idl 或 .h 文件，并在语句后 `importlib` 。

## <a name="example"></a>示例

下面的代码显示在 .cpp 文件中：

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|任何位置|
|**且**|是|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[独立属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[包括](include-cpp.md)<br/>
[importlib](importlib.md)
