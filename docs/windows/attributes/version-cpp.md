---
description: '了解详细信息：版本 (c + +) '
title: '版本 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 5b6d13e59b36fe37d71c9e2cca6fe7d75587f77b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118298"
---
# <a name="version-c"></a>version (C++)

标识类的多个版本中的特定版本。

## <a name="syntax"></a>语法

```cpp
[ version("version") ]
```

### <a name="parameters"></a>parameters

*version*<br/>
`coclass` 的版本号。 如果未指定，则将1.0 放置在 .idl 文件中。

## <a name="remarks"></a>备注

**版本** c + + 特性具有与 [版本](/windows/win32/Midl/version)MIDL 特性相同的功能，并将传递到生成的 .idl 文件。

## <a name="example"></a>示例

有关 **版本** 的示例用法，请参阅可 [绑定](bindable.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**`class`**, **`struct`**|
|**且**|否|
|**必需属性**|**coclass**|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[编译器特性](compiler-attributes.md)<br/>
[类特性](class-attributes.md)
