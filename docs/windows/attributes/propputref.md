---
description: 了解详细信息： propputref
title: 'propputref (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: 5f09d742ef0df75df03e4f4d740181cfcaaa8f2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329674"
---
# <a name="propputref"></a>propputref

指定使用引用而不是值的属性设置函数。

## <a name="syntax"></a>语法

```cpp
[propputref]
```

## <a name="remarks"></a>备注

**Propputref** c + + 特性具有与 [propputref](/windows/win32/Midl/propputref) MIDL 特性相同的功能。

## <a name="example"></a>示例

有关 **propputref** 的示例用法，请参阅可 [绑定](bindable.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|`propget`, `propput`|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)
