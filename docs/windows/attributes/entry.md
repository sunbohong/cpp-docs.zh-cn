---
title: '项 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 63e5ccebb1d3844af8dd11b4b094abe96e3e257c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845310"
---
# <a name="entry"></a>entry

通过标识 DLL 中的入口点，在模块中指定导出的函数或常量。

## <a name="syntax"></a>语法

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>参数

*id*<br/>
入口点的 ID。

## <a name="remarks"></a>注解

**Entry** c + + 属性具有与[entry](/windows/win32/Midl/entry) MIDL 属性相同的功能。

## <a name="example"></a>示例

有关**条目**的示例用法，请参阅[idl_module](idl-module.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|`idl_module` 特性|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)
