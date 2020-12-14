---
description: 了解详细信息：条目
title: '项 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: fbceea4c23d730ceba780ce68398a9d78fa9c33b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259222"
---
# <a name="entry"></a>entry

通过标识 DLL 中的入口点，在模块中指定导出的函数或常量。

## <a name="syntax"></a>语法

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>parameters

*id*<br/>
入口点的 ID。

## <a name="remarks"></a>备注

**Entry** c + + 属性具有与 [entry](/windows/win32/Midl/entry) MIDL 属性相同的功能。

## <a name="example"></a>示例

有关 **条目** 的示例用法，请参阅 [idl_module](idl-module.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|`idl_module` 特性|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)
