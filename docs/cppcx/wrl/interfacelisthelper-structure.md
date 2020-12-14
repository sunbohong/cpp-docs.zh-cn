---
description: 了解详细信息： InterfaceListHelper 结构
title: InterfaceListHelper 结构
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: ca9e13e66acb6f27fba76a7653388305c57146dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249797"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template <
    typename T0,
    typename T1 = Nil,
    typename T2 = Nil,
    typename T3 = Nil,
    typename T4 = Nil,
    typename T5 = Nil,
    typename T6 = Nil,
    typename T7 = Nil,
    typename T8 = Nil,
    typename T9 = Nil
>
struct InterfaceListHelper;

template <typename T0>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>parameters

*T0*<br/>
模板参数0，这是必需的。

*T1*<br/>
模板参数1，默认情况下未指定。

*T2*<br/>
模板参数2，默认情况下未指定。第三个模板参数。

*T3*<br/>
模板参数3，默认情况下未指定。

*T4*<br/>
模板参数4，默认情况下未指定。

*T5*<br/>
模板参数5，默认情况下未指定。

*T6*<br/>
模板参数6，默认情况下未指定。

*T7*<br/>
模板参数7，默认情况下未指定。

*T8*<br/>
模板参数8，默认情况下未指定。

*T9*<br/>
模板参数9，默认情况下未指定。

## <a name="remarks"></a>备注

`InterfaceList`通过递归应用指定的模板参数参数生成类型。

**InterfaceListHelper** 模板使用模板参数 *T0* 来定义结构中的第一个数据成员 `InterfaceList` ，然后以递归方式将 **InterfaceListHelper** 模板应用到任何剩余的模板参数。 当没有剩余的模板参数时， **InterfaceListHelper** 将停止。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`TypeT`|InterfaceList 类型的同义词。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`InterfaceListHelper`

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="see-also"></a>请参阅

[Microsoft：： WRL：:D etails 命名空间](microsoft-wrl-details-namespace.md)
