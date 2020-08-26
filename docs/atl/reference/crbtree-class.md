---
title: CRBTree 类
ms.date: 11/04/2016
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
ms.openlocfilehash: 7b8e47b5cd0ac278711947abc867956333371be3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833486"
---
# <a name="crbtree-class"></a>CRBTree 类

此类提供用于创建和使用红黑树的方法。

## <a name="syntax"></a>语法

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
```

#### <a name="parameters"></a>参数

*温度*<br/>
键元素类型。

*向量*<br/>
值元素类型。

*KTraits*<br/>
用于复制或移动关键元素的代码。 有关更多详细信息，请参阅 [CElementTraits 类](../../atl/reference/celementtraits-class.md) 。

*VTraits*<br/>
用于复制或移动值元素的代码。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|说明|
|----------|-----------------|
|[CRBTree::KINARGTYPE](#kinargtype)|当键作为输入参数传递时使用的类型。|
|[CRBTree::KOUTARGTYPE](#koutargtype)|当键作为输出参数返回时使用的类型。|
|[CRBTree::VINARGTYPE](#vinargtype)|将值作为输入参数传递时使用的类型。|
|[CRBTree::VOUTARGTYPE](#voutargtype)|将值作为输出参数传递时使用的类型。|

### <a name="public-classes"></a>公共类

|名称|说明|
|----------|-----------------|
|[CRBTree：： CPair 类](#cpair_class)|一个包含键和值元素的类。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|说明|
|----------|-----------------|
|[CRBTree：： ~ CRBTree](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|说明|
|----------|-----------------|
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|调用此方法可查找使用下一个可用键的元素的位置。|
|[CRBTree：： GetAt](#getat)|调用此方法可在树中的给定位置获取元素。|
|[CRBTree：： GetCount](#getcount)|调用此方法可获取树中的元素数。|
|[CRBTree::GetHeadPosition](#getheadposition)|调用此方法可获取树开头的元素的位置值。|
|[CRBTree::GetKeyAt](#getkeyat)|调用此方法可从树中的给定位置获取键。|
|[CRBTree：： GetNext](#getnext)|调用此方法以获取指向存储在对象中的元素的指针 `CRBTree` ，并将该位置前移到下一个元素。|
|[CRBTree::GetNextAssoc](#getnextassoc)|调用此方法可获取存储在映射中的元素的键和值，并将位置前移到下一个元素。|
|[CRBTree::GetNextKey](#getnextkey)|调用此方法可获取存储在树中的元素的键，并将位置前移到下一个元素。|
|[CRBTree::GetNextValue](#getnextvalue)|调用此方法可获取存储在树中的元素的值，并将位置前移到下一个元素。|
|[CRBTree::GetPrev](#getprev)|调用此方法以获取指向存储在对象中的元素的指针 `CRBTree` ，然后将该位置更新为上一个元素。|
|[CRBTree::GetTailPosition](#gettailposition)|调用此方法可获取树尾部元素的位置值。|
|[CRBTree::GetValueAt](#getvalueat)|调用此方法可以检索存储在对象中的指定位置的值 `CRBTree` 。|
|[CRBTree：： IsEmpty](#isempty)|调用此方法可测试空的树对象。|
|[CRBTree：： RemoveAll](#removeall)|调用此方法可从对象中移除所有元素 `CRBTree` 。|
|[CRBTree：： RemoveAt](#removeat)|调用此方法可删除对象中给定位置的元素 `CRBTree` 。|
|[CRBTree::SetValueAt](#setvalueat)|调用此方法可更改存储在对象中指定位置的值 `CRBTree` 。|

## <a name="remarks"></a>注解

红色-黑色树是一个二元搜索树，它为每个节点使用额外的信息，以确保其保持 "平衡"，也就是说，树高度不会以不太大的比例增长，因而会影响性能。

此模板类设计为由 [CRBMap](../../atl/reference/crbmap-class.md) 和 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)使用。 构成这些派生类的大部分方法由提供 `CRBTree` 。

有关各种集合类及其功能和性能特征的更完整讨论，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a> CRBTree：： CPair 类

一个包含键和值元素的类。

```
class CPair : public __POSITION
```

### <a name="remarks"></a>注解

此类由 [CRBTree：： GetAt](#getat)、 [CRBTree：： GetNext](#getnext)和 [CRBTree：： GetPrev](#getprev) 方法用来访问存储在树结构中的键和值元素。

成员如下：

|数据成员|说明|
|-|-|
|`m_key`|存储密钥元素的数据成员。|
|`m_value`|存储 value 元素的数据成员。|

## <a name="crbtreecrbtree"></a><a name="dtor"></a> CRBTree：： ~ CRBTree

析构函数。

```
~CRBTree() throw();
```

### <a name="remarks"></a>注解

释放所有已分配的资源。 调用 [CRBTree：： RemoveAll](#removeall) 以删除所有元素。

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a> CRBTree::FindFirstKeyAfter

调用此方法可查找使用下一个可用键的元素的位置。

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>参数

*键*<br/>
键值。

### <a name="return-value"></a>返回值

返回使用下一个可用键的元素的位置值。 如果没有更多元素，则返回 NULL。

### <a name="remarks"></a>注解

此方法可以轻松地遍历树，无需事先计算位置值。

## <a name="crbtreegetat"></a><a name="getat"></a> CRBTree：： GetAt

调用此方法可在树中的给定位置获取元素。

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>参数

*位置*<br/>
位置值。

*键*<br/>
接收密钥的变量。

*value*<br/>
接收值的变量。

### <a name="return-value"></a>返回值

前两个窗体返回指向 [CPair](#cpair_class)的指针。 第三个窗体获取给定位置的键和值。

### <a name="remarks"></a>注解

位置值可以通过调用方法（如 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： GetTailPosition](#gettailposition)）来确定。

在调试版本中，如果 *pos* 等于 NULL，则将发生断言失败。

## <a name="crbtreegetcount"></a><a name="getcount"></a> CRBTree：： GetCount

调用此方法可获取树中的元素数。

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>返回值

返回元素数， (每个键/值对都是存储在树中) 一个元素。

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a> CRBTree::GetHeadPosition

调用此方法可获取树开头的元素的位置值。

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>返回值

返回树开头的元素的位置值。

### <a name="remarks"></a>注解

返回的值 `GetHeadPosition` 可用于方法 [CRBTree：： GetKeyAt](#getkeyat) 或 [CRBTree：： GetNext](#getnext) 等方法遍历树并检索值。

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a> CRBTree::GetKeyAt

调用此方法可从树中的给定位置获取键。

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>参数

*位置*<br/>
位置值。

### <a name="return-value"></a>返回值

返回 *存储在树中位置位置* 的键。

### <a name="remarks"></a>注解

如果 *pos* 不是有效的位置值，则结果是不可预知的。 在调试版本中，如果 *pos* 等于 NULL，则将发生断言失败。

## <a name="crbtreegetnext"></a><a name="getnext"></a> CRBTree：： GetNext

调用此方法以获取指向存储在对象中的元素的指针 `CRBTree` ，并将该位置前移到下一个元素。

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

### <a name="return-value"></a>返回值

返回一个指针，该指针指向树中的下一个 [CPair](#cpair_class) 值。

### <a name="remarks"></a>注解

每次调用后， *pos* 位置计数器就会更新。 如果检索到的元素是树中的最后一个，则 *pos* 将设置为 NULL。

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a> CRBTree::GetNextAssoc

调用此方法可获取存储在映射中的元素的键和值，并将位置前移到下一个元素。

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

*键*<br/>
指定树的键类型的模板参数。

*value*<br/>
指定树值类型的模板参数。

### <a name="remarks"></a>注解

每次调用后， *pos* 位置计数器就会更新。 如果检索到的元素是树中的最后一个，则 *pos* 将设置为 NULL。

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a> CRBTree::GetNextKey

调用此方法可获取存储在树中的元素的键，并将位置前移到下一个元素。

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

### <a name="return-value"></a>返回值

返回对树中的下一个键的引用。

### <a name="remarks"></a>注解

更新当前位置计数器， *pos*。如果树中没有更多条目，则位置计数器设置为 NULL。

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a> CRBTree::GetNextValue

调用此方法可获取存储在树中的元素的值，并将位置前移到下一个元素。

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

### <a name="return-value"></a>返回值

返回对树中下一个值的引用。

### <a name="remarks"></a>注解

更新当前位置计数器， *pos*。如果树中没有更多条目，则位置计数器设置为 NULL。

## <a name="crbtreegetprev"></a><a name="getprev"></a> CRBTree::GetPrev

调用此方法以获取指向存储在对象中的元素的指针 `CRBTree` ，然后将该位置更新为上一个元素。

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

### <a name="return-value"></a>返回值

返回一个指向存储在树中的上一个 [CPair](#cpair_class) 值的指针。

### <a name="remarks"></a>注解

更新当前位置计数器， *pos*。如果树中没有更多条目，则位置计数器设置为 NULL。

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a> CRBTree::GetTailPosition

调用此方法可获取树尾部元素的位置值。

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>返回值

返回树尾部元素的位置值。

### <a name="remarks"></a>注解

返回的值 `GetTailPosition` 可用于方法 [CRBTree：： GetKeyAt](#getkeyat) 或 [CRBTree：： GetPrev](#getprev) 等方法遍历树并检索值。

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a> CRBTree::GetValueAt

调用此方法可以检索存储在对象中的指定位置的值 `CRBTree` 。

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

### <a name="return-value"></a>返回值

返回对存储在对象中的给定位置的值的引用 `CRBTree` 。

## <a name="crbtreeisempty"></a><a name="isempty"></a> CRBTree：： IsEmpty

调用此方法可测试空的树对象。

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>返回值

如果树为空，则返回 TRUE，否则返回 FALSE。

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a> CRBTree::KINARGTYPE

当键作为输入参数传递时使用的类型。

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a> CRBTree::KOUTARGTYPE

当键作为输出参数返回时使用的类型。

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a> CRBTree：： RemoveAll

调用此方法可从对象中移除所有元素 `CRBTree` 。

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>注解

清除 `CRBTree` 对象，释放用于存储元素的内存。

## <a name="crbtreeremoveat"></a><a name="removeat"></a> CRBTree：： RemoveAt

调用此方法可删除对象中给定位置的元素 `CRBTree` 。

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

### <a name="remarks"></a>注解

删除存储在指定位置的键/值对。 将释放用于存储元素的内存。 *Pos*引用的位置变为无效，并且树中任何其他元素的位置保持有效，它们不一定保持相同的顺序。

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a> CRBTree::SetValueAt

调用此方法可更改存储在对象中指定位置的值 `CRBTree` 。

```cpp
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>参数

*位置*<br/>
位置计数器，由先前对 [CRBTree：： GetHeadPosition](#getheadposition) 或 [CRBTree：： FindFirstKeyAfter](#findfirstkeyafter)等方法的调用返回。

*value*<br/>
要添加到对象的值 `CRBTree` 。

### <a name="remarks"></a>注解

更改存储在对象中给定位置的值元素 `CRBTree` 。

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a> CRBTree::VINARGTYPE

将值作为输入参数传递时使用的类型。

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a> CRBTree::VOUTARGTYPE

将值作为输出参数传递时使用的类型。

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>另请参阅

[类概述](../../atl/atl-class-overview.md)
