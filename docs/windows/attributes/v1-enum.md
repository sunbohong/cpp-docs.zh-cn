---
description: 了解详细信息： v1_enum
title: 'v1_enum (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: c096ec78971e8980b68572c7f0bbb4510d03d3d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327195"
---
# <a name="v1_enum"></a>v1_enum

指示指定的枚举类型传输为32位实体，而不是16位默认值。

## <a name="syntax"></a>语法

```cpp
[v1_enum]
```

## <a name="remarks"></a>备注

**V1_enum** c + + 特性具有与 [v1_enum](/windows/win32/Midl/v1-enum) MIDL 特性相同的功能。

## <a name="example"></a>示例

以下代码演示了如何使用 **v1_enum**：

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|枚举类型|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)
