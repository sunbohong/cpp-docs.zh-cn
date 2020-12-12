---
description: '了解详细信息：对象 (c + +) '
title: '对象 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: 82f259f6ca36c44f33eb68970d8b76ae2acc5853
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329749"
---
# <a name="object-c"></a>object (C++)

标识自定义接口。

## <a name="syntax"></a>语法

```cpp
[object]
```

## <a name="remarks"></a>备注

在接口定义前面时， **对象** c + + 特性会使接口作为自定义接口放置在 .idl 文件中。

标记有对象的任何接口都必须从继承 `IUnknown` 。 如果任何基接口从继承，则满足此条件 `IUnknown` 。 如果没有基接口从继承 `IUnknown` ，则编译器将导致用 **对象** 标记的接口派生自 `IUnknown` 。

## <a name="example"></a>示例

有关如何使用 **对象** 的示例，请参阅 [nonbrowsable](nonbrowsable.md) 。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**interface**|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[接口特性](interface-attributes.md)<br/>
[双重](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[客户](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
