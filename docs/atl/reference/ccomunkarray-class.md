---
description: 了解详细信息： CComUnkArray 类
title: CComUnkArray 类
ms.date: 11/04/2016
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
ms.openlocfilehash: e03022fb751b487debb9f81d9e3d99ce46f1b9e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142137"
---
# <a name="ccomunkarray-class"></a>CComUnkArray 类

此类存储 `IUnknown` 指针，旨在用作 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 模板类的参数。

## <a name="syntax"></a>语法

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>parameters

*nMaxSize*<br/>
`IUnknown`静态数组中可包含的最大指针数。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComUnkArray::CComUnkArray](#ccomunkarray)|构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComUnkArray：： Add](#add)|调用此方法可添加指向 `IUnknown` 该数组的指针。|
|[CComUnkArray：： begin](#begin)|返回指向集合中第一个 `IUnknown` 指针的指针。|
|[CComUnkArray：： end](#end)|返回指向集合中最后一个指针之后的一个指针 `IUnknown` 。|
|[CComUnkArray：： System.windows.application.getcookie](#getcookie)|调用此方法以获取与给定指针关联的 cookie `IUnknown` 。|
|[CComUnkArray::GetUnknown](#getunknown)|调用此方法以获取 `IUnknown` 与给定 cookie 关联的指针。|
|[CComUnkArray：： Remove](#remove)|调用此方法可 `IUnknown` 从数组中删除指针。|

## <a name="remarks"></a>备注

`CComUnkArray` 保存固定数目的 `IUnknown` 指针，其中每个都是连接点上的接口。 `CComUnkArray` 可用作 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 模板类的参数。 `CComUnkArray<1>` 是的模板特殊化，已针对 `CComUnkArray` 一个连接点进行了优化。

`CComUnkArray`方法[开始](#begin)和[结束](#end)可用于循环遍历所有连接点 (例如，在) 引发事件时。

有关自动创建连接点代理的详细信息，请参阅向 [对象添加连接点](../../atl/adding-connection-points-to-an-object.md) 。

> [!NOTE]
> **注意** 类 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) 由 **添加类** 向导在创建具有连接点的控件时使用。 如果要手动指定连接点的数目，请将引用从更改 `CComDynamicUnkArray` 为 `CComUnkArray<` *n* `>` ，其中 *n* 是所需的连接点的数目。

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ccomunkarrayadd"></a><a name="add"></a> CComUnkArray：： Add

调用此方法可添加指向 `IUnknown` 该数组的指针。

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>parameters

*pUnk*<br/>
调用此方法可添加指向 `IUnknown` 该数组的指针。

### <a name="return-value"></a>返回值

返回与新添加的指针关联的 cookie; 如果数组的大小不足以包含新指针，则返回0。

## <a name="ccomunkarraybegin"></a><a name="begin"></a> CComUnkArray：： begin

返回指向接口指针集合的开头的指针 `IUnknown` 。

```
IUnknown**
    begin();
```

### <a name="return-value"></a>返回值

指向 `IUnknown` 接口指针的指针。

### <a name="remarks"></a>备注

集合包含指向本地存储的接口的指针 `IUnknown` 。 将每个 `IUnknown` 接口强制转换为实际接口类型，然后调用它。 不需要先查询接口。

使用接口之前 `IUnknown` ，应检查其是否不为 NULL。

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a> CComUnkArray::CComUnkArray

构造函数。

```
CComUnkArray();
```

### <a name="remarks"></a>备注

设置用于保存指针的集合 `nMaxSize` `IUnknown` ，并将指针初始化为 NULL。

## <a name="ccomunkarrayend"></a><a name="end"></a> CComUnkArray：： end

返回指向集合中最后一个指针之后的一个指针 `IUnknown` 。

```
IUnknown**
    end();
```

### <a name="return-value"></a>返回值

指向 `IUnknown` 接口指针的指针。

### <a name="remarks"></a>备注

`CComUnkArray`方法 `begin` 和 `end` 可用于循环遍历所有连接点，例如，在触发事件时。

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a> CComUnkArray：： System.windows.application.getcookie

调用此方法以获取与给定指针关联的 cookie `IUnknown` 。

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>parameters

*ppFind*<br/>
`IUnknown`需要相关 cookie 的指针。

### <a name="return-value"></a>返回值

返回与指针关联的 cookie `IUnknown` ; 如果找不到匹配的指针，则返回 0 `IUnknown` 。

### <a name="remarks"></a>备注

如果有多个相同指针的实例，则 `IUnknown` 此函数将返回第一个实例的 cookie。

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a> CComUnkArray::GetUnknown

调用此方法以获取 `IUnknown` 与给定 cookie 关联的指针。

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>parameters

*dwCookie*<br/>
需要关联指针的 cookie `IUnknown` 。

### <a name="return-value"></a>返回值

返回 `IUnknown` 指针，或者如果找不到匹配的 cookie，则为 NULL。

## <a name="ccomunkarrayremove"></a><a name="remove"></a> CComUnkArray：： Remove

调用此方法可 `IUnknown` 从数组中删除指针。

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>parameters

*dwCookie*<br/>
引用 `IUnknown` 要从数组中移除的指针的 cookie。

### <a name="return-value"></a>返回值

如果删除指针，则返回 TRUE，否则返回 FALSE。

## <a name="see-also"></a>请参阅

[CComDynamicUnkArray 类](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
