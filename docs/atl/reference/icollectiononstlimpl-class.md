---
description: 了解详细信息： ICollectionOnSTLImpl 类
title: ICollectionOnSTLImpl 类
ms.date: 11/04/2016
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
ms.openlocfilehash: 089fc0fbd8f410d740646e2a653b076d32448647
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139601"
---
# <a name="icollectiononstlimpl-class"></a>ICollectionOnSTLImpl 类

此类提供集合类使用的方法。

## <a name="syntax"></a>语法

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>parameters

*T*<br/>
COM 集合接口。

*CollType*<br/>
C + + 标准库容器类。

*ItemType*<br/>
容器接口公开的项的类型。

*CopyItem*<br/>
[复制策略类](../../atl/atl-copy-policy-classes.md)。

*EnumType*<br/>
与 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)兼容的枚举器类。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[ICollectionOnSTLImpl：： get__NewEnum](#newenum)|返回集合的枚举器对象。|
|[ICollectionOnSTLImpl：： getcount](#get_count)|返回集合中元素的数目。|
|[ICollectionOnSTLImpl：： get_Item](#get_item)|返回集合中请求的项。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[ICollectionOnSTLImpl：： m_coll](#m_coll)|集合。|

## <a name="remarks"></a>备注

此类为集合接口的三个方法提供实现： [getcount](#get_count)、 [get_Item](#get_item)和 [get__NewEnum](#newenum)。

使用此类：

- 定义 (或借用) 要实现的集合接口。

- 基于此集合接口从的专用化派生类 `ICollectionOnSTLImpl` 。

- 使用派生类实现未由处理的集合接口中的任何方法 `ICollectionOnSTLImpl` 。

> [!NOTE]
> 如果集合接口为双重接口，请从 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)派生你的类， `ICollectionOnSTLImpl` 如果你希望 ATL 提供方法的实现，则将专用化作为第一个模板参数传递 `IDispatch` 。

- 向 [m_coll](#m_coll) 成员添加项以填充集合。

有关详细信息和示例，请参阅 [ATL 集合和枚举](../../atl/atl-collections-and-enumerators.md)器。

## <a name="inheritance-hierarchy"></a>继承层次结构

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a> ICollectionOnSTLImpl：： getcount

此方法返回集合中的项数。

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>parameters

*pcount*<br/>
弄集合中元素的数目。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a> ICollectionOnSTLImpl：： get_Item

此方法返回集合中的指定项。

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>parameters

*Index*<br/>
中集合中项的从1开始的索引。

*pvar*<br/>
弄与 *Index* 相对应的项。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

通过使用在专用化中作为模板参数传递的[复制策略类](../../atl/atl-copy-policy-classes.md)的 copy 方法，将[m_coll](#m_coll)中指定位置的数据复制到该项 `ICollectionOnSTLImpl` 。

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a> ICollectionOnSTLImpl：： get__NewEnum

返回集合的枚举器对象。

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>parameters

*ppUnk*<br/>
弄新创建的枚举数对象的 **IUnknown** 指针。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

新创建的枚举器在原始集合上维护迭代器， `m_coll` (因此不会进行任何复制) 并在集合对象上保留 COM 引用，以确保在存在未完成的枚举器时集合保持活动状态。

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a> ICollectionOnSTLImpl：： m_coll

此成员保存集合所表示的项。

```
CollType m_coll;
```

## <a name="see-also"></a>请参阅

[ATLCollections 示例](../../overview/visual-cpp-samples.md)<br/>
[类概述](../../atl/atl-class-overview.md)
