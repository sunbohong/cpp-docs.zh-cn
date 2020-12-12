---
description: '详细了解：在 (c + +) '
title: '在 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: c4d19fcf7adc767986306a3ef55b26a2cc91dccf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321371"
---
# <a name="in-c"></a>in (C++)

指示参数将从调用过程传递给被调用过程。

## <a name="syntax"></a>语法

```cpp
[in]
```

## <a name="remarks"></a>备注

C + + 特性具有 [与 MIDL 特性](/windows/win32/Midl/in)**相同的功能**。

## <a name="example"></a>示例

有关如何 **在中** 使用的示例，请参阅可 [绑定](bindable.md)。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|Interface 参数，interface 方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|**retval**|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[参数属性](parameter-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[值](defaultvalue.md)<br/>
[id](id.md)<br/>
[out](out-cpp.md)
