---
description: 了解详细信息： CSimpleArray 类
title: CSimpleArray 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: 95750662587c7ab47500a338c3ecd7e74a92eb34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140784"
---
# <a name="csimplearray-class"></a>CSimpleArray 类

此类提供用于管理简单数组的方法。

## <a name="syntax"></a>语法

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在数组中的数据的类型。

*TEqual*<br/>
特征对象，定义类型为 *T* 的元素的相等性测试。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|简单数组的构造函数。|
|[CSimpleArray：： ~ CSimpleArray](#dtor)|简单数组的析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleArray：： Add](#add)|将新元素添加到数组中。|
|[CSimpleArray：： Find](#find)|查找数组中的元素。|
|[CSimpleArray：：](#getdata)|返回一个指向存储在数组中的数据的指针。|
|[CSimpleArray：： GetSize](#getsize)|返回数组中存储的元素数。|
|[CSimpleArray：： Remove](#remove)|从数组中移除给定元素。|
|[CSimpleArray：： RemoveAll](#removeall)|从数组中移除所有元素。|
|[CSimpleArray：： RemoveAt](#removeat)|从数组中移除指定的元素。|
|[CSimpleArray::SetAtIndex](#setatindex)|设置数组中的指定元素。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|从数组中检索元素。|
|[CSimpleArray：： operator =](#operator_eq)|赋值运算符。|

## <a name="remarks"></a>备注

`CSimpleArray` 提供用于创建和管理任意给定类型的简单数组的方法 `T` 。

参数 `TEqual` 提供了一种为类型为的两个元素定义相等函数的方法 `T` 。 通过创建类似于 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)的类，可以更改任何给定数组的相等性测试的行为。 例如，处理指针数组时，根据指针所引用的值定义相等性可能会很有用。 默认实现利用 **operator = ( # B1**。

`CSimpleArray`和[CSimpleMap](../../atl/reference/csimplemap-class.md)都是为少量元素而设计的。 当数组包含大量元素时，应使用[CAtlArray](../../atl/reference/catlarray-class.md)和[CAtlMap](../../atl/reference/catlmap-class.md) 。

## <a name="requirements"></a>要求

**标头：** atlsimpcoll

## <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a> CSimpleArray：： Add

将新元素添加到数组中。

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>parameters

*t*<br/>
要添加到数组中的元素。

### <a name="return-value"></a>返回值

如果元素已成功添加到数组，则返回 TRUE，否则返回 FALSE。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a> CSimpleArray::CSimpleArray

数组对象的构造函数。

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>parameters

*src*<br/>
一个现有的 `CSimpleArray` 对象。

### <a name="remarks"></a>备注

初始化数据成员、创建新的空 `CSimpleArray` 对象或现有对象的副本 `CSimpleArray` 。

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a> CSimpleArray：： ~ CSimpleArray

析构函数。

```
~CSimpleArray();
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

## <a name="csimplearrayfind"></a><a name="find"></a> CSimpleArray：： Find

查找数组中的元素。

```
int Find(const T& t) const;
```

### <a name="parameters"></a>parameters

*t*<br/>
要搜索的元素。

### <a name="return-value"></a>返回值

返回找到的元素的索引; 如果未找到该元素，则返回-1。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a> CSimpleArray：：

返回一个指向存储在数组中的数据的指针。

```
T* GetData() const;
```

### <a name="return-value"></a>返回值

返回一个指向数组中的数据的指针。

## <a name="csimplearraygetsize"></a><a name="getsize"></a> CSimpleArray：： GetSize

返回数组中存储的元素数。

```
int GetSize() const;
```

### <a name="return-value"></a>返回值

返回数组中存储的元素数。

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a> CSimpleArray：： operator \[\]

从数组中检索元素。

```
T& operator[](int nindex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
元素索引。

### <a name="return-value"></a>返回值

返回由 *nIndex* 引用的数组的元素。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a> CSimpleArray：： operator =

赋值运算符。

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>parameters

*src*<br/>
要复制的数组。

### <a name="return-value"></a>返回值

返回一个指向已更新的 `CSimpleArray` 对象的指针。

### <a name="remarks"></a>备注

将所有元素从 `CSimpleArray` *src* 引用的对象复制到当前数组对象中，并替换所有现有数据。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a> CSimpleArray：： Remove

从数组中移除给定元素。

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>parameters

*t*<br/>
要从数组中移除的元素。

### <a name="return-value"></a>返回值

如果找到并移除该元素，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

删除元素后，数组中的剩余元素将重新编号，以填充空白区域。

## <a name="csimplearrayremoveall"></a><a name="removeall"></a> CSimpleArray：： RemoveAll

从数组中移除所有元素。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>备注

删除当前存储在数组中的所有元素。

## <a name="csimplearrayremoveat"></a><a name="removeat"></a> CSimpleArray：： RemoveAt

从数组中移除指定的元素。

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
指向要移除的元素的索引。

### <a name="return-value"></a>返回值

如果该元素已移除，则返回 TRUE; 如果索引无效，则返回 FALSE。

### <a name="remarks"></a>备注

删除元素后，数组中的剩余元素将重新编号，以填充空白区域。

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a> CSimpleArray::SetAtIndex

设置数组中的指定元素。

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
要更改的元素的索引。

*t*<br/>
要分配给指定元素的值。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE; 如果索引无效，则返回 FALSE。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
