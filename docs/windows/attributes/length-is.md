---
description: 了解详细信息： length_is
title: 'length_is (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: b3f913819b88958f294aee42f4cbda07827fa990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329846"
---
# <a name="length_is"></a>length_is

指定要传输的数组元素的数目。

## <a name="syntax"></a>语法

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>参数

*expression*<br/>
一个或多个 C 语言表达式。 允许空参数槽。

## <a name="remarks"></a>备注

**Length_is** c + + 特性具有与 [length_is](/windows/win32/Midl/length-is) MIDL 特性相同的功能。

## <a name="example"></a>示例

有关如何指定数组的部分的示例，请参阅 [first_is](first-is.md) 。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|或中的字段 **`struct`** **`union`** ，接口参数，接口方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)<br/>
[参数属性](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[last_is](last-is.md)<br/>
[size_is](size-is.md)
