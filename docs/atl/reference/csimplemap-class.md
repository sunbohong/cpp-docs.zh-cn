---
description: 了解详细信息： CSimpleMap 类
title: CSimpleMap 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
ms.openlocfilehash: 66640e3fcd325d59b82a10d98188a6fcd74ca79d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140616"
---
# <a name="csimplemap-class"></a>CSimpleMap 类

此类提供对简单映射数组的支持。

## <a name="syntax"></a>语法

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>parameters

*TKey*<br/>
键元素类型。

*TVal*<br/>
值元素类型。

*TEqual*<br/>
特征对象，定义类型的元素的相等性测试 `T` 。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CSimpleMap：： _ArrayElementType](#_arrayelementtype)|值类型的 Typedef。|
|[CSimpleMap：： _ArrayKeyType](#_arraykeytype)|Key 类型的 Typedef。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|构造函数。|
|[CSimpleMap：： ~ CSimpleMap](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleMap：： Add](#add)|向映射数组添加键和关联值。|
|[CSimpleMap：： Map.findkey](#findkey)|查找特定的键。|
|[CSimpleMap::FindVal](#findval)|查找特定的值。|
|[CSimpleMap::GetKeyAt](#getkeyat)|检索指定的键。|
|[CSimpleMap：： GetSize](#getsize)|返回映射数组中的项数。|
|[CSimpleMap::GetValueAt](#getvalueat)|检索指定的值。|
|[CSimpleMap：： Lookup](#lookup)|返回与给定键关联的值。|
|[CSimpleMap：： Remove](#remove)|删除键和匹配值。|
|[CSimpleMap：： RemoveAll](#removeall)|删除所有键和值。|
|[CSimpleMap：： RemoveAt](#removeat)|删除特定的键和匹配值。|
|[CSimpleMap::ReverseLookup](#reverselookup)|返回与给定值相关联的键。|
|[CSimpleMap：： SetAt](#setat)|设置与给定键关联的值。|
|[CSimpleMap::SetAtIndex](#setatindex)|设置特定的键和值。|

## <a name="remarks"></a>备注

`CSimpleMap` 提供对任意给定类型的简单映射数组的支持 `T` ，并管理关键元素的无序数组及其关联值。

参数 `TEqual` 提供了一种为类型为的两个元素定义相等函数的方法 `T` 。 通过创建类似于 [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)的类，可以更改任何给定数组的相等性测试的行为。 例如，处理指针数组时，根据指针所引用的值定义相等性可能会很有用。 默认实现利用 **operator = = ( # B1**。

`CSimpleMap`提供和[CSimpleArray](../../atl/reference/csimplearray-class.md)是为了与以前的 ATL 版本兼容，而[CAtlArray](../../atl/reference/catlarray-class.md)和[CAtlMap](../../atl/reference/catlmap-class.md)提供了更完整且高效的集合实现。

与 ATL 和 MFC 中的其他映射集合不同，此类是使用简单数组实现的，并且查找搜索需要线性搜索。 `CAtlMap` 当数组包含大量元素时，应使用。

## <a name="requirements"></a>要求

**标头：** atlsimpcoll

## <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a> CSimpleMap：： Add

向映射数组添加键和关联值。

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>parameters

*key*<br/>
键。

*初始值*<br/>
关联的值。

### <a name="return-value"></a>返回值

如果已成功添加键和值，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

添加的每个键和值对都将导致映射数组内存被释放并重新分配，以确保每个的数据都是连续存储的。 也就是说，第二个关键元素始终紧随内存中的第一个键元素，依此类推。

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a> CSimpleMap：： _ArrayElementType

键类型的 typedef。

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a> CSimpleMap：： _ArrayKeyType

值类型的 typedef。

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a> CSimpleMap::CSimpleMap

构造函数。

```
CSimpleMap();
```

### <a name="remarks"></a>备注

初始化数据成员。

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a> CSimpleMap：： ~ CSimpleMap

析构函数。

```
~CSimpleMap();
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

## <a name="csimplemapfindkey"></a><a name="findkey"></a> CSimpleMap：： Map.findkey

查找特定的键。

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>parameters

*key*<br/>
要搜索的键。

### <a name="return-value"></a>返回值

如果找到，则返回该项的索引; 否则返回-1。

## <a name="csimplemapfindval"></a><a name="findval"></a> CSimpleMap::FindVal

查找特定的值。

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>parameters

*初始值*<br/>
要搜索的值。

### <a name="return-value"></a>返回值

如果找到该值，则返回该值的索引; 否则返回-1。

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a> CSimpleMap::GetKeyAt

检索指定索引处的键。

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
要返回的键的索引。

### <a name="return-value"></a>返回值

返回由 *nIndex* 引用的键。

### <a name="remarks"></a>备注

*NIndex* 传递的索引必须有效，才能使返回值有意义。

## <a name="csimplemapgetsize"></a><a name="getsize"></a> CSimpleMap：： GetSize

返回映射数组中的项数。

```
int GetSize() const;
```

### <a name="return-value"></a>返回值

返回键 (项的数目，并且值是映射数组中的一项) 。

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a> CSimpleMap::GetValueAt

检索特定索引处的值。

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
要返回的值的索引。

### <a name="return-value"></a>返回值

返回 *nIndex* 引用的值。

### <a name="remarks"></a>备注

*NIndex* 传递的索引必须有效，才能使返回值有意义。

## <a name="csimplemaplookup"></a><a name="lookup"></a> CSimpleMap：： Lookup

返回与给定键关联的值。

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>parameters

*key*<br/>
键。

### <a name="return-value"></a>返回值

返回关联的值。 如果找不到匹配的键，则返回 NULL。

## <a name="csimplemapremove"></a><a name="remove"></a> CSimpleMap：： Remove

删除键和匹配值。

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>parameters

*key*<br/>
键。

### <a name="return-value"></a>返回值

如果成功删除了键和匹配值，则返回 TRUE，否则返回 FALSE。

## <a name="csimplemapremoveall"></a><a name="removeall"></a> CSimpleMap：： RemoveAll

删除所有键和值。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>备注

从映射数组对象中移除所有键和值。

## <a name="csimplemapremoveat"></a><a name="removeat"></a> CSimpleMap：： RemoveAt

删除指定索引处的键和关联值。

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
要移除的键和关联的值的索引。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE; 如果指定的索引为无效的索引，则为 FALSE。

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a> CSimpleMap::ReverseLookup

返回与给定值相关联的键。

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>parameters

*初始值*<br/>
值。

### <a name="return-value"></a>返回值

返回关联的键。 如果找不到匹配的键，则返回 NULL。

## <a name="csimplemapsetat"></a><a name="setat"></a> CSimpleMap：： SetAt

设置与给定键关联的值。

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>parameters

*key*<br/>
键。

*初始值*<br/>
要分配的新值。

### <a name="return-value"></a>返回值

如果找到了该键并且值已成功更改，则返回 TRUE; 否则返回 FALSE。

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a> CSimpleMap::SetAtIndex

设置指定索引处的键和值。

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
引用要更改的键和值对的索引。

*key*<br/>
新键。

*初始值*<br/>
新值。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE; 如果索引无效，则返回 FALSE。

### <a name="remarks"></a>备注

更新 *nIndex* 所指向的键和值。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
