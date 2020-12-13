---
description: 了解详细信息： IEnumOnSTLImpl 类
title: IEnumOnSTLImpl 类
ms.date: 11/04/2016
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
ms.openlocfilehash: 33bc34288ebd03f987532ebb078fed62ce2204c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139485"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl 类

此类定义基于 c + + 标准库集合的枚举器接口。

## <a name="syntax"></a>语法

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>parameters

*基座*<br/>
COM 枚举器。 有关示例，请参阅 [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) 。

*piid*<br/>
指向枚举器接口的接口 ID 的指针。

*T*<br/>
枚举器接口公开的项的类型。

*复制*<br/>
[复制策略类](../../atl/atl-copy-policy-classes.md)。

*CollType*<br/>
C + + 标准库容器类。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IEnumOnSTLImpl：： Clone](#clone)|**克隆** 的实现。|
|[IEnumOnSTLImpl：： Init](#init)|初始化枚举器。|
|[IEnumOnSTLImpl：： Next](#next)|**下一步** 的实现。|
|[IEnumOnSTLImpl：： Reset](#reset)|**重置** 的实现。|
|[IEnumOnSTLImpl：： Skip](#skip)|**Skip** 的实现。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[IEnumOnSTLImpl：： m_iter](#m_iter)|表示枚举器在集合内的当前位置的迭代器。|
|[IEnumOnSTLImpl：： m_pcollection](#m_pcollection)|一个指针，指向包含要枚举的项的 c + + 标准库容器。|
|[IEnumOnSTLImpl：： m_spUnk](#m_spunk)|`IUnknown`提供集合的对象的指针。|

## <a name="remarks"></a>备注

`IEnumOnSTLImpl` 提供要枚举的项存储在与 c + + 标准库兼容的容器中的 COM 枚举器接口的实现。 此类类似于 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) 类，该类提供基于数组的枚举器接口的实现。

> [!NOTE]
> 有关和之间的进一步差异的详细信息，请参阅 [CComEnumImpl：： Init](../../atl/reference/ccomenumimpl-class.md#init) `CComEnumImpl` `IEnumOnSTLImpl` 。

通常，您 *不* 需要通过从此接口实现派生来创建自己的枚举器类。 如果要使用基于 c + + 标准库容器的基于 ATL 的枚举器，则更常见的方法是创建 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)的实例，或创建一个集合类，该集合类通过从 [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)派生来返回一个枚举器。

但是，如果确实需要提供自定义枚举器 (例如，其中一个公开接口以及枚举器接口) ，则可以从此类派生。 在这种情况下，您可能需要重写 [Clone](#clone) 方法以提供您自己的实现。

## <a name="inheritance-hierarchy"></a>继承层次结构

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ienumonstlimplinit"></a><a name="init"></a> IEnumOnSTLImpl：： Init

初始化枚举器。

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>parameters

*pUnkForRelease*<br/>
中 `IUnknown` 必须在枚举器的生存期内保持活动状态的对象的指针。 如果不存在此类对象，则传递 NULL。

*集合*<br/>
对包含要枚举的项的 c + + 标准库容器的引用。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

如果将 `Init` 引用传递给保存在另一个对象中的集合，则可以使用 *pUnkForRelease* 参数来确保只要枚举器需要，就可以使用参数来确保该对象及其包含的集合。

必须先调用此方法，然后再将指向枚举器接口的指针传递回任何客户端。

## <a name="ienumonstlimplclone"></a><a name="clone"></a> IEnumOnSTLImpl：： Clone

此方法通过创建类型为的对象 `CComEnumOnSTL` ，并使用当前对象所使用的同一集合和迭代器对其进行初始化，并返回新创建的对象上的接口，来提供 Clone 方法的实现。

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>parameters

*ppEnum*<br/>
弄从当前枚举器克隆的新创建对象上的枚举器接口。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="ienumonstlimplm_spunk"></a><a name="m_spunk"></a> IEnumOnSTLImpl：： m_spUnk

`IUnknown`提供集合的对象的指针。

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>备注

此智能指针维护对传递给 [IEnumOnSTLImpl：： Init](#init)的对象的引用，确保它在枚举器的生存期内保持活动状态。

## <a name="ienumonstlimplm_pcollection"></a><a name="m_pcollection"></a> IEnumOnSTLImpl：： m_pcollection

此成员指向提供驱动程序实现枚举器接口的数据的集合。

```
CollType* m_pcollection;
```

### <a name="remarks"></a>备注

通过调用 [IEnumOnSTLImpl：： Init](#init)初始化此成员。

## <a name="ienumonstlimplm_iter"></a><a name="m_iter"></a> IEnumOnSTLImpl：： m_iter

此成员包含用于标记集合中当前位置的迭代器，并导航到后续元素。

```
CollType::iterator m_iter;
```

## <a name="ienumonstlimplnext"></a><a name="next"></a> IEnumOnSTLImpl：： Next

此方法提供了 **下一** 方法的实现。

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>parameters

*celt*<br/>
中请求的元素的数目。

*rgelt*<br/>
弄要用元素填充的数组。

*pceltFetched*<br/>
弄在 *rgelt* 中实际返回的元素数。 如果列表中保留的元素数少于 *celt* ，则此项可以小于 *celt* 。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="ienumonstlimplreset"></a><a name="reset"></a> IEnumOnSTLImpl：： Reset

此方法提供 **Reset** 方法的实现。

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="ienumonstlimplskip"></a><a name="skip"></a> IEnumOnSTLImpl：： Skip

此方法提供 **Skip** 方法的实现。

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>parameters

*celt*<br/>
中要跳过的元素的数目。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
