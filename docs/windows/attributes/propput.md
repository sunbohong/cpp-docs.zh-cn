---
title: 'propput (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: 11f216dd183f3977aee9af90c6579d01cad45fdf
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839941"
---
# <a name="propput"></a>propput

指定属性设置功能。

## <a name="syntax"></a>语法

```cpp
[propput]
```

## <a name="remarks"></a>备注

**Propput** c + + 特性具有与[propput](/windows/win32/Midl/propput) MIDL 特性相同的功能。

## <a name="example"></a>示例

有关**propput**的示例用法，请参阅可[绑定](bindable.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|`propget`, `propputref`|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)
