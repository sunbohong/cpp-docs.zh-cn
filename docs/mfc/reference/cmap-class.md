---
description: 了解详细信息： CMap 类
title: CMap 类
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: ff88d205608cc87f06d28e6d2d4b647c35909efa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207899"
---
# <a name="cmap-class"></a>CMap 类

将唯一键映射到值的字典集合类。

## <a name="syntax"></a>语法

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>parameters

*KEY*<br/>
用作映射键的对象的类。

*ARG_KEY*<br/>
用于 *密钥* 参数的数据类型;通常是对 *密钥* 的引用。

*VALUE*<br/>
存储在映射中的对象的类。

*ARG_VALUE*<br/>
用于 *值* 参数的数据类型;通常是对 *值* 的引用。

## <a name="members"></a>成员

### <a name="public-structures"></a>公共结构

|名称|描述|
|----------|-----------------|
|[CMap：： CPair](#cpair)|一个嵌套结构，其中包含键值和关联对象的值。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMap：： CMap](#cmap)|构造一个将键映射到值的集合。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMap：： GetCount](#getcount)|返回此映射中的元素数。|
|[CMap：： GetHashTableSize](#gethashtablesize)|返回哈希表中的元素数。|
|[CMap：： GetNextAssoc](#getnextassoc)|获取用于循环访问的下一个元素。|
|[CMap：： GetSize](#getsize)|返回此映射中的元素数。|
|[CMap：： GetStartPosition](#getstartposition)|返回第一个元素的位置。|
|[CMap：： InitHashTable](#inithashtable)|初始化哈希表并指定其大小。|
|[CMap：： IsEmpty](#isempty)|测试空映射条件 (不) 任何元素。|
|[CMap：： Lookup](#lookup)|查找映射到给定键的值。|
|[CMap：:P GetFirstAssoc](#pgetfirstassoc)|返回指向第一个元素的指针。|
|[CMap：:P GetNextAssoc](#pgetnextassoc)|获取指向要循环访问的下一个元素的指针。|
|[CMap：:P 查找](#plookup)|返回一个指向其值与指定值匹配的键的指针。|
|[CMap：： RemoveAll](#removeall)|从此映射中移除所有元素。|
|[CMap：： RemoveKey](#removekey)|移除由键指定的元素。|
|[CMap：： SetAt](#setat)|将元素插入到映射中;如果找到匹配的键，则替换现有元素。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CMap：： operator \[\]](#operator_at)|将元素插入到映射中-的运算符替换 `SetAt` 。|

## <a name="remarks"></a>备注

将键/值对插入到映射 () 元素中后，就可以使用密钥对其进行访问，从而有效地检索或删除该对。 还可以循环访问映射中的所有元素。

"位置" 类型的变量用于对项的替代访问。 您可以使用一个位置来 "记住" 一项，然后循环访问该映射。 您可能认为此迭代是按键值顺序进行的;不是。 检索到的元素的序列是不确定的。

此类的某些成员函数调用全局 helper 函数，这些函数必须针对该类的大多数用途进行自定义 `CMap` 。 请参阅 **MFC 参考** 的宏和全局部分中的 [集合类帮助](../../mfc/reference/collection-class-helpers.md)器。

`CMap` 重写 [CObject：：串行化](../../mfc/reference/cobject-class.md#serialize) 以支持其元素的序列化和转储。 如果使用将映射存储到存档 `Serialize` ，则每个地图元素将依次序列化。 Helper 函数的默认实现 `SerializeElements` 执行按位写入。 有关从或其他用户定义类型的指针集合项的序列化的信息 `CObject` ，请参阅 [如何：生成 Type-Safe 集合](../../mfc/how-to-make-a-type-safe-collection.md)。

如果需要映射中单个元素的诊断转储 () 的键和值，则必须将转储上下文的深度设置为1或更大。

`CMap`删除对象时，或删除其元素时，将删除这些键和值。

映射类派生类似于列表派生。 有关专用列表类的派生的说明，请参阅文章 [集合](../../mfc/collections.md) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>要求

**标头：** afxtempl.h

## <a name="cmapcmap"></a><a name="cmap"></a> CMap：： CMap

构造空映射。

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>parameters

*nBlockSize*<br/>
指定用于扩展映射的内存分配粒度。

### <a name="remarks"></a>备注

随着地图的增长，内存是以 *nBlockSize* 项的单位分配的。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a> CMap：： CPair

包含一个键值和关联的对象的值。

### <a name="remarks"></a>备注

这是 [CMap](../../mfc/reference/cmap-class.md)类中的嵌套结构。

结构由以下两个字段组成：

- `key` 键类型的实际值。

- `value` 关联的对象的值。

它用于存储来自 [CMap：:P lookup](#plookup)、 [CMap：:P getfirstassoc](#pgetfirstassoc)和 [CMap：:P getnextassoc](#pgetnextassoc)的返回值。

### <a name="example"></a>示例

有关用法示例，请参阅 [CMap：:P lookup](#plookup)的示例。

## <a name="cmapgetcount"></a><a name="getcount"></a> CMap：： GetCount

检索映射中的元素数目。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>返回值

元素数量。

### <a name="example"></a>示例

请参阅 [CMap：： Lookup](#lookup)的示例。

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a> CMap：： GetHashTableSize

确定映射的哈希表中的元素数。

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>返回值

哈希表中的元素数。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a> CMap：： GetNextAssoc

检索中的 map 元素 `rNextPosition` ，然后更新 `rNextPosition` 以引用映射中的下一个元素。

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>parameters

*rNextPosition*<br/>
指定对上一个或调用返回的位置值的 `GetNextAssoc` 引用 `GetStartPosition` 。

*KEY*<br/>
指定地图键类型的模板参数。

*rKey*<br/>
指定检索到的元素的返回键。

*VALUE*<br/>
指定地图值类型的模板参数。

*右值*<br/>
指定检索到的元素的返回值。

### <a name="remarks"></a>备注

此函数最适用于遍历映射中的所有元素。 请注意，位置序列不一定与键值序列相同。

如果检索到的元素是映射中的最后一个，则 *rNextPosition* 的新值将设置为 NULL。

### <a name="example"></a>示例

请参阅 [CMap：： SetAt](#setat)的示例。

## <a name="cmapgetsize"></a><a name="getsize"></a> CMap：： GetSize

返回地图元素的数目。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>返回值

映射中的项数。

### <a name="remarks"></a>备注

调用此方法可检索映射中的元素数。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a> CMap：： GetStartPosition

通过返回可传递给调用的位置值来启动映射迭代 `GetNextAssoc` 。

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>返回值

一个位置值，该值指示循环访问映射的起始位置;如果映射为空，则为 NULL。

### <a name="remarks"></a>备注

迭代顺序不可预测;因此，"映射中的第一个元素" 没有特别的意义。

### <a name="example"></a>示例

请参阅 [CMap：： SetAt](#setat)的示例。

## <a name="cmapinithashtable"></a><a name="inithashtable"></a> CMap：： InitHashTable

初始化哈希表。

```cpp
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>parameters

*hashSize*<br/>
哈希表中的项数。

*bAllocNow*<br/>
如果为 TRUE，则在初始化时分配哈希表;否则，将根据需要分配表。

### <a name="remarks"></a>备注

为了获得最佳性能，哈希表的大小应为质数。 若要最大程度地减少冲突，大小应大约比预期的最大数据集大20%。

### <a name="example"></a>示例

请参阅 [CMap：： Lookup](#lookup)的示例。

## <a name="cmapisempty"></a><a name="isempty"></a> CMap：： IsEmpty

确定映射是否为空。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>返回值

如果此映射不包含任何元素，则为非零值;否则为0。

### <a name="example"></a>示例

请参阅 [CMap：： RemoveAll](#removeall)的示例。

## <a name="cmaplookup"></a><a name="lookup"></a> CMap：： Lookup

查找映射到给定键的值。

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>parameters

*ARG_KEY*<br/>
指定 *键值* 类型的模板参数。

*key*<br/>
指定标识要查找的元素的键。

*VALUE*<br/>
指定要查找的值的类型。

*右值*<br/>
接收查找值。

### <a name="return-value"></a>返回值

如果找到元素，则为非零值;否则为0。

### <a name="remarks"></a>备注

`Lookup` 使用哈希算法快速查找映射元素，该元素具有与给定键完全匹配的键。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a> CMap：： operator []

成员函数的便利替换 `SetAt` 。

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>parameters

*VALUE*<br/>
指定地图值类型的模板参数。

*ARG_KEY*<br/>
指定键值类型的模板参数。

*key*<br/>
用于从映射中检索值的键。

### <a name="remarks"></a>备注

因此，它只能用于赋值语句左侧 (左值) 。 如果没有具有指定键的 map 元素，则创建一个新元素。

由于可能在映射中找不到键，因此没有 "右边" (r-值) 与此运算符等效。 使用 `Lookup` 成员函数进行元素检索。

### <a name="example"></a>示例

请参阅 [CMap：： Lookup](#lookup)的示例。

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a> CMap：:P GetFirstAssoc

返回 map 对象的第一个条目。

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>返回值

指向映射中第一项的指针;请参阅 [CMap：： CPair](#cpair)。 如果映射不包含任何项，则该值为 NULL。

### <a name="remarks"></a>备注

调用此函数可返回指向 map 对象中第一个元素的指针。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a> CMap：:P GetNextAssoc

检索由 *pAssocRec* 指向的地图元素。

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>parameters

*pAssocRet*<br/>
指向以前的 [PGetNextAssoc](#pgetnextassoc) 或 [CMap：:P getfirstassoc](#pgetfirstassoc) 调用返回的映射条目。

### <a name="return-value"></a>返回值

指向映射中下一项的指针;请参阅 [CMap：： CPair](#cpair)。 如果该元素是映射中的最后一个，则该值为 NULL。

### <a name="remarks"></a>备注

调用此方法可循环访问映射中的所有元素。 使用对的调用检索第一个元素 `PGetFirstAssoc` ，并通过连续调用来循环访问该映射 `PGetNextAssoc` 。

### <a name="example"></a>示例

请参阅 [CMap：:P getfirstassoc](#pgetfirstassoc)的示例。

## <a name="cmapplookup"></a><a name="plookup"></a> CMap：:P 查找

查找映射到给定键的值。

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>parameters

*key*<br/>
要搜索的元素的键。

### <a name="return-value"></a>返回值

指向键结构的指针;请参阅 [CMap：： CPair](#cpair)。 如果未找到匹配项，则 `CMap::PLookup` 返回 NULL。

### <a name="remarks"></a>备注

调用此方法以搜索其键与给定键完全匹配的地图元素。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a> CMap：： RemoveAll

通过调用全局 helper 函数，从此映射中移除所有值 `DestructElements` 。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>备注

如果映射已为空，则函数可以正常工作。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a> CMap：： RemoveKey

查找与提供的键相对应的映射项;如果找到该密钥，则删除该条目。

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>parameters

*ARG_KEY*<br/>
指定密钥类型的模板参数。

*key*<br/>
要移除的元素的键。

### <a name="return-value"></a>返回值

如果已找到并成功删除该项，则为非零值;否则为0。

### <a name="remarks"></a>备注

`DestructElements`Helper 函数用于删除条目。

### <a name="example"></a>示例

请参阅 [CMap：： SetAt](#setat)的示例。

## <a name="cmapsetat"></a><a name="setat"></a> CMap：： SetAt

在映射中插入元素的主要方法。

```cpp
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>parameters

*ARG_KEY*<br/>
指定 *密钥* 参数类型的模板参数。

*key*<br/>
指定新元素的键。

*ARG_VALUE*<br/>
指定 *newValue* 参数类型的模板参数。

*newValue*<br/>
指定新元素的值。

### <a name="remarks"></a>备注

首先，查找该密钥。 如果找到该键，则相应的值将更改;否则，将创建新的键值对。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>请参阅

[MFC 示例收集](../../overview/visual-cpp-samples.md)<br/>
[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)
