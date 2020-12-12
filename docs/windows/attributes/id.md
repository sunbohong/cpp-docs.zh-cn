---
description: 了解详细信息： id
title: 'id (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 04f7144e1c6f8b6655b0b6be23e0ffa4f22dc27c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180196"
---
# <a name="id"></a>id

在接口或调度接口) 中，为成员函数指定一个用于 (属性或方法的 *dispid* 参数。

## <a name="syntax"></a>语法

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>parameters

*dispid*<br/>
接口方法的调度 ID。

## <a name="remarks"></a>备注

**Id** c + + 属性具有与 [id](/windows/win32/Midl/id) MIDL 属性相同的功能。

## <a name="example"></a>示例

有关如何使用 **id** 的示例，请参阅可 [绑定](bindable.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|接口方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[数据成员特性](data-member-attributes.md)<br/>
[值](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)
