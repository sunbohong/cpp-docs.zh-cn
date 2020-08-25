---
title: 'local (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: dea62653478e451af00fa47b72984f3b580aadc0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834084"
---
# <a name="local-c"></a>local (C++)

在 interface 标头中使用时，允许将 MIDL 编译器用作标头生成器。 在单独的函数中使用时，指定不会为其生成存根的本地过程。

## <a name="syntax"></a>语法

```cpp
[local]
```

## <a name="remarks"></a>备注

**本地**c + + 特性具有与[本地](/windows/win32/Midl/local)MIDL 特性相同的功能。

## <a name="example"></a>示例

有关如何使用**local**的示例，请参阅[call_as](call-as.md) 。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**interface**、interface 方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|`dispinterface`|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[接口特性](interface-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[call_as](call-as.md)
