---
description: 了解详细信息： CRBMap 类
title: CRBMap 类
ms.date: 11/04/2016
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
ms.openlocfilehash: 55d96bfd2c7b043bdbdc4c1ee1f329c9b77b9ca9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141045"
---
# <a name="crbmap-class"></a>CRBMap 类

此类表示使用 Red-Black 二进制树的映射结构。

## <a name="syntax"></a>语法

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMap::CRBMap](#crbmap)|构造函数。|
|[CRBMap：： ~ CRBMap](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CRBMap：： Lookup](#lookup)|调用此方法可查找对象中的键或值 `CRBMap` 。|
|[CRBMap::RemoveKey](#removekey)|调用此方法可从对象中删除元素 `CRBMap` （给定键）。|
|[CRBMap：： SetAt](#setat)|调用此方法可将元素对插入到映射中。|

## <a name="remarks"></a>备注

`CRBMap` 提供对任意给定类型的映射数组的支持，并管理关键元素的有序数组及其关联值。 每个键只能有一个关联值。 使用 [CRBMap：： SetAt](#setat) 方法 (包含键和值) 的元素存储在二进制树结构中。 可以使用 [CRBMap：： RemoveKey](#removekey) 方法删除元素，这将删除具有给定键值的元素。

可以通过以下方法（如 [CRBTree：： GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)、 [CRBTree：： GetNext](../../atl/reference/crbtree-class.md#getnext)和 [CRBTree：： GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)）遍历树。

*KTraits* 和 *VTraits* 参数是包含复制或移动元素所需的任何补充代码的特征类。

`CRBMap` 派生自 [CRBTree](../../atl/reference/crbtree-class.md)，后者使用 Red-Black 算法实现一个二元树。 [CRBMultiMap](../../atl/reference/crbmultimap-class.md) 是允许每个键有多个值的变体。 它也派生自 `CRBTree` ，因此与共享许多功能 `CRBMap` 。

`CRBMap`和都 `CRBMultiMap` 是[CAtlMap](../../atl/reference/catlmap-class.md)类提供的替代方法。 当只需存储少量元素时，请考虑改用 [CSimpleMap](../../atl/reference/csimplemap-class.md) 类。

有关各种集合类及其功能和性能特征的更完整讨论，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="crbmapcrbmap"></a><a name="crbmap"></a> CRBMap::CRBMap

构造函数。

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>parameters

*nBlockSize*<br/>
块大小。

### <a name="remarks"></a>备注

*NBlockSize* 参数是在需要新元素时分配的内存量的度量值。 较大的块大小可减少对内存分配例程的调用，但会占用更多资源。 默认情况下，将为10个元素一次分配空间。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a> CRBMap：： ~ CRBMap

析构函数。

```
~CRBMap() throw();
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

## <a name="crbmaplookup"></a><a name="lookup"></a> CRBMap：： Lookup

调用此方法可查找对象中的键或值 `CRBMap` 。

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>parameters

*key*<br/>
指定标识要查找的元素的键。

*value*<br/>
接收查找值的变量。

### <a name="return-value"></a>返回值

如果找到该键，则该方法的第一种形式将返回 true，否则返回 false。 第二个和第三个窗体返回指向 [CPair](crbtree-class.md#cpair_class)的指针。

### <a name="remarks"></a>备注

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a> CRBMap::RemoveKey

调用此方法可从对象中删除元素 `CRBMap` （给定键）。

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>parameters

*key*<br/>
与要移除的元素对相对应的键。

### <a name="return-value"></a>返回值

如果找到并移除该键，则返回 true; 如果失败，则返回 false。

### <a name="remarks"></a>备注

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a> CRBMap：： SetAt

调用此方法可将元素对插入到映射中。

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>parameters

*key*<br/>
要添加到对象的键值 `CRBMap` 。

*value*<br/>
要添加到对象的值 `CRBMap` 。

### <a name="return-value"></a>返回值

返回对象中键/值元素对的位置 `CRBMap` 。

### <a name="remarks"></a>备注

`SetAt` 如果找到匹配的键，则替换现有元素。 如果未找到该键，则创建一个新的键/值对。

有关可用的其他方法的信息，请参阅基类 [CRBTree](../../atl/reference/crbtree-class.md) 的文档。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>请参阅

[CRBTree 类](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap 类](../../atl/reference/catlmap-class.md)<br/>
[CRBMultiMap 类](../../atl/reference/crbmultimap-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
