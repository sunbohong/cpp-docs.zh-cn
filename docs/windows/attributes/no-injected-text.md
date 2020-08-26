---
title: 'no_injected_text (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: ab718376d5da7214813d5ab2e0caaa7bbccd077b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844075"
---
# <a name="no_injected_text"></a>no_injected_text

阻止编译器将代码注入到属性使用的结果中。

## <a name="syntax"></a>语法

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>参数

*boolean*<br/>
 (可选) **`true`** 如果不插入代码，则 **`false`** 允许注入代码。 **`true`** 默认值为。

## <a name="remarks"></a>注解

**No_injected_text** c + + 特性最常见的用法是[/fx](../../build/reference/fx-merge-injected-code.md)编译器选项，该选项将**no_injected_text**特性插入到 .mrg 文件中。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|任何位置|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[编译器特性](compiler-attributes.md)
