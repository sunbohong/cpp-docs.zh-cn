---
description: 了解详细信息： importlib
title: 'importlib (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: f3000be3415ed944d621ebcd36442e33951efc84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114944"
---
# <a name="importlib"></a>importlib

使已编译到另一个类型库中的类型可供所创建的类型库使用。

## <a name="syntax"></a>语法

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>parameters

*tlb_file*<br/>
要导入当前项目类型库中的 .tlb 文件的名称（用引号引起来）。

## <a name="remarks"></a>备注

**Importlib** c + + 特性导致 `importlib` 语句放置在生成的 .idl 文件的库块中。 **Importlib** 特性具有与 [importlib](/windows/win32/Midl/importlib) MIDL 特性相同的功能。

## <a name="example"></a>示例

以下代码显示了如何使用 **importlib** 的示例：

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|任何位置|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[编译器特性](compiler-attributes.md)<br/>
[独立属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[包括](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
