---
description: 了解详细信息： CRBMultiMap 类
title: CRBMultiMap 类
ms.date: 11/04/2016
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
ms.openlocfilehash: 8dfe644521cb7ec4135c5c1f71d36371ac1706ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141019"
---
# <a name="crbmultimap-class"></a>CRBMultiMap 类

此类表示一个映射结构，该结构允许每个键与多个值相关联，同时使用 Red-Black 的二进制树。

## <a name="syntax"></a>语法

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>parameters

*K*<br/>
键元素类型。

*V*<br/>
值元素类型。

*KTraits*<br/>
用于复制或移动关键元素的代码。 有关更多详细信息，请参阅 [CElementTraits 类](../../atl/reference/celementtraits-class.md) 。

*VTraits*<br/>
用于复制或移动值元素的代码。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|构造函数。|
|[CRBMultiMap：： ~ CRBMultiMap](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|调用此方法可查找第一个具有给定键的元素的位置。|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|调用此方法以获取与给定键关联的值，并更新位置值。|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|调用此方法以获取与给定键关联的元素，并更新位置值。|
|[CRBMultiMap：： Insert](#insert)|调用此方法可将元素对插入到映射中。|
|[CRBMultiMap::RemoveKey](#removekey)|调用此方法可删除给定键的所有键/值元素。|

## <a name="remarks"></a>备注

`CRBMultiMap` 提供对任意给定类型的映射数组的支持，从而管理键元素和值的有序数组。 与 [CRBMap](../../atl/reference/crbmap-class.md) 类不同，每个键可以与多个值相关联。

使用 [CRBMultiMap：： Insert](#insert) 方法 (包含键和值) 的元素存储在二进制树结构中。 可以使用 [CRBMultiMap：： RemoveKey](#removekey) 方法删除元素，此方法将删除与给定键匹配的所有元素。

可以通过以下方法（如 [CRBTree：： GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)、 [CRBTree：： GetNext](../../atl/reference/crbtree-class.md#getnext)和 [CRBTree：： GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)）遍历树。 使用 [CRBMultiMap：： FindFirstWithKey](#findfirstwithkey)、 [CRBMultiMap：： GetNextValueWithKey](#getnextvaluewithkey)和 [CRBMultiMap：： GetNextWithKey](#getnextwithkey) 方法访问每个键可能具有多个值。 有关此操作的示例，请参阅 [CRBMultiMap：： CRBMultiMap](#crbmultimap) 的示例。

*KTraits* 和 *VTraits* 参数是包含复制或移动元素所需的任何补充代码的特征类。

`CRBMultiMap` 派生自 [CRBTree](../../atl/reference/crbtree-class.md)，后者使用 Red-Black 算法实现一个二元树。 和的替代 `CRBMultiMap` 方法 `CRBMap` 由 [CAtlMap](../../atl/reference/catlmap-class.md) 类提供。 当只需存储少量元素时，请考虑改用 [CSimpleMap](../../atl/reference/csimplemap-class.md) 类。

有关各种集合类及其功能和性能特征的更完整讨论，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a> CRBMultiMap::CRBMultiMap

构造函数。

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>parameters

*nBlockSize*<br/>
块大小。

### <a name="remarks"></a>备注

*NBlockSize* 参数是在需要新元素时分配的内存量的度量值。 较大的块大小可减少对内存分配例程的调用，但会占用更多资源。 默认情况下，将为10个元素一次分配空间。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a> CRBMultiMap：： ~ CRBMultiMap

析构函数。

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a> CRBMultiMap::FindFirstWithKey

调用此方法可查找第一个具有给定键的元素的位置。

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>parameters

*key*<br/>
指定标识要查找的元素的键。

### <a name="return-value"></a>返回值

如果找到该键，则返回第一个键/值元素的位置，否则返回 NULL。

### <a name="remarks"></a>备注

中的键 `CRBMultiMap` 可以有一个或多个关联值。 此方法将提供第一个值 (的位置值，实际上，这可能是唯一) 与该特定键相关联的值。 然后，可以将返回的位置值与 [CRBMultiMap：： GetNextValueWithKey](#getnextvaluewithkey) 或 [CRBMultiMap：： GetNextWithKey](#getnextwithkey) 结合使用，以获取值并更新位置。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

请参阅 [CRBMultiMap：： CRBMultiMap](#crbmultimap)的示例。

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a> CRBMultiMap::GetNextValueWithKey

调用此方法以获取与给定键关联的值并更新位置值。

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>参数

pos<br/>
位置值，通过调用 [CRBMultiMap：： FindFirstWithKey](#findfirstwithkey) 或 [CRBMultiMap：： GetNextWithKey](#getnextwithkey)获取，或对的前一次调用获取 `GetNextValueWithKey` 。

*key*<br/>
指定标识要查找的元素的键。

### <a name="return-value"></a>返回值

返回与给定键关联的元素对。

### <a name="remarks"></a>备注

位置值将更新为指向与该键关联的下一个值。 如果没有更多值，则将位置值设置为 NULL。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

请参阅 [CRBMultiMap：： CRBMultiMap](#crbmultimap)的示例。

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a> CRBMultiMap::GetNextWithKey

调用此方法以获取与给定键关联的元素并更新位置值。

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>参数

pos<br/>
位置值，通过调用 [CRBMultiMap：： FindFirstWithKey](#findfirstwithkey) 或 [CRBMultiMap：： GetNextValueWithKey](#getnextvaluewithkey)获取，或对的前一次调用获取 `GetNextWithKey` 。

*key*<br/>
指定标识要查找的元素的键。

### <a name="return-value"></a>返回值

返回与给定键关联的下一个 [CRBTree：： CPair 类](crbtree-class.md#cpair_class) 元素。

### <a name="remarks"></a>备注

位置值将更新为指向与该键关联的下一个值。 如果没有更多值，则将位置值设置为 NULL。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

## <a name="crbmultimapinsert"></a><a name="insert"></a> CRBMultiMap：： Insert

调用此方法可将元素对插入到映射中。

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>parameters

*key*<br/>
要添加到对象的键值 `CRBMultiMap` 。

*value*<br/>
要添加到对象的值 `CRBMultiMap` ，与 *键* 关联。

### <a name="return-value"></a>返回值

返回对象中键/值元素对的位置 `CRBMultiMap` 。

### <a name="remarks"></a>备注

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

请参阅 [CRBMultiMap：： CRBMultiMap](#crbmultimap)的示例。

## <a name="crbmultimapremovekey"></a><a name="removekey"></a> CRBMultiMap::RemoveKey

调用此方法可删除给定键的所有键/值元素。

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>parameters

*key*<br/>
指定标识要删除)  (元素的键。

### <a name="return-value"></a>返回值

返回与给定键关联的值的数目。

### <a name="remarks"></a>备注

`RemoveKey` 删除具有匹配 *键* 的键的所有键/值元素。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

请参阅 [CRBMultiMap：： CRBMultiMap](#crbmultimap)的示例。

## <a name="see-also"></a>请参阅

[CRBTree 类](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap 类](../../atl/reference/catlmap-class.md)<br/>
[CRBMap 类](../../atl/reference/crbmap-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
