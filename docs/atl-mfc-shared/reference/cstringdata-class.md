---
description: 了解详细信息： CStringData 类
title: CStringData 类
ms.date: 11/04/2016
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
ms.openlocfilehash: 74bf3563cb5dca506498ceef05ddc84f13c44f41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166585"
---
# <a name="cstringdata-class"></a>CStringData 类

此类表示字符串对象的数据。

## <a name="syntax"></a>语法

```
struct CStringData
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|描述|
|-|-|
|[AddRef](#addref)|递增字符串数据对象的引用计数。|
|[data](#data)|检索字符串对象的字符数据。|
|[IsLocked](#islocked)|确定关联的字符串对象的缓冲区是否被锁定。|
|[IsShared](#isshared)|确定关联的字符串对象的缓冲区当前是否共享。|
|[Lock](#lock)|锁定关联的字符串对象的缓冲区。|
|[版本](#release)|释放指定的字符串对象。|
|[Unlock](#unlock)|解锁关联的字符串对象的缓冲区。|

### <a name="data-members"></a>数据成员

|名称|描述|
|-|-|
|[nAllocLength](#nalloclength)|中已分配数据的长度 `XCHAR` (不包括终止 null) |
|[nDataLength](#ndatalength)|S 中当前使用的数据的长度 `XCHAR` (不包括终止 null) |
|[nRefs](#nrefs)|对象的当前引用计数。|
|[pStringMgr](#pstringmgr)|指向此字符串对象的字符串管理器的指针。|

## <a name="remarks"></a>备注

此类应仅由实现自定义字符串管理器的开发人员使用。 有关自定义字符串管理器的详细信息，请参阅 [内存管理和 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)

此类封装了各种类型的信息和与更高的字符串对象相关的数据，例如 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)或 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) 对象。 每个较高的字符串对象都包含指向其关联对象的指针 `CStringData` ，允许多个字符串对象指向相同的字符串数据对象。 此关系由对象的引用计数 (`nRefs`) 表示 `CStringData` 。

> [!NOTE]
> 在某些情况下，字符串类型 (如 `CFixedString`) 将不会共享包含多个字符串对象的字符串数据对象。 有关此内容的详细信息，请参阅 [内存管理和 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)。

此数据由以下内容组成：

- 内存管理器 (类型为 [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) 字符串。

- 当前长度 ( 字符串的 [nDataLength](#ndatalength)) 。

- 分配的长度 ( 字符串的 [nAllocLength](#nalloclength)) 。 出于性能原因，这可能不同于当前字符串长度

- 对象的当前引用计数 ( [nRefs](#nrefs)) `CStringData` 。 此值用于确定共享同一对象的字符串对象的数量 `CStringData` 。

- 实际字符缓冲区 ( 字符串的 [数据](#data)) 。

   > [!NOTE]
   > 字符串对象的实际字符缓冲区由字符串管理器分配，并追加到 `CStringData` 对象。

## <a name="requirements"></a>要求

**标头：** atlsimpstr

## <a name="cstringdataaddref"></a><a name="addref"></a> CStringData：： AddRef

递增字符串对象的引用计数。

```cpp
void AddRef() throw();
```

### <a name="remarks"></a>备注

递增字符串对象的引用计数。

> [!NOTE]
> 不要对引用计数为负值的字符串调用此方法，因为负计数指示字符串缓冲区已锁定。

## <a name="cstringdatadata"></a><a name="data"></a> CStringData：:d ata

返回指向字符串对象的字符缓冲区的指针。

```cpp
void* data() throw();
```

### <a name="return-value"></a>返回值

指向字符串对象的字符缓冲区的指针。

### <a name="remarks"></a>备注

调用此函数可返回关联字符串对象的当前字符缓冲区。

> [!NOTE]
> 此缓冲区不是由对象分配， `CStringData` 而是在需要时由字符串管理器分配。 当分配时，缓冲区将追加到字符串数据对象。

## <a name="cstringdataislocked"></a><a name="islocked"></a> CStringData：： IsLocked

确定字符缓冲区是否已锁定。

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>返回值

如果缓冲区被锁定，则返回 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可确定字符串对象的字符缓冲区当前是否处于锁定状态。

## <a name="cstringdataisshared"></a><a name="isshared"></a> CStringData::IsShared

确定是否共享字符缓冲区。

```
bool IsShared() const throw();
```

### <a name="return-value"></a>返回值

如果缓冲区是共享的，则返回 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可确定字符串数据对象的字符缓冲区当前是否在多个字符串对象之间共享。

## <a name="cstringdatalock"></a><a name="lock"></a> CStringData：： Lock

锁定关联的字符串对象的字符缓冲区。

```cpp
void Lock() throw();
```

### <a name="remarks"></a>备注

调用此函数可锁定字符串数据对象的字符缓冲区。 当开发人员需要直接访问字符缓冲区时，可以使用锁定和解锁。 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)和[UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)方法演示了锁定的一个很好示例 `CSimpleStringT` 。

> [!NOTE]
> 只有在更高版本的字符串对象之间未共享缓冲区时，才可以锁定字符缓冲区。

## <a name="cstringdatanalloclength"></a><a name="nalloclength"></a> CStringData::nAllocLength

已分配的字符缓冲区的长度。

```
int nAllocLength;
```

### <a name="remarks"></a>备注

在中存储已分配数据缓冲区的长度， `XCHAR` 不包括终止 null)  (。

## <a name="cstringdatandatalength"></a><a name="ndatalength"></a> CStringData::nDataLength

字符串对象的当前长度。

```
int nDataLength;
```

### <a name="remarks"></a>备注

将当前使用的数据的长度存储 `XCHAR` (不包括终止 null) 。

## <a name="cstringdatanrefs"></a><a name="nrefs"></a> CStringData::nRefs

字符串数据对象的引用计数。

```
long nRefs;
```

### <a name="remarks"></a>备注

存储字符串数据对象的引用计数。 此计数指示与字符串数据对象相关联的字符串对象的数量。 负值表示字符串数据对象当前已锁定。

## <a name="cstringdatapstringmgr"></a><a name="pstringmgr"></a> CStringData：:p StringMgr

关联的字符串对象的内存管理器。

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>备注

存储关联的字符串对象的内存管理器。 有关内存管理器和字符串的详细信息，请参阅 [内存管理和 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)。

## <a name="cstringdatarelease"></a><a name="release"></a> CStringData：： Release

递减字符串数据对象的引用计数。

```cpp
void Release() throw();
```

### <a name="remarks"></a>备注

如果引用数达到零，则调用此函数以减少引用计数，释放 `CStringData` 结构。 这通常是在删除字符串对象时完成的，因此不再需要引用字符串数据对象。

例如，以下代码将 `CStringData::Release` 为与关联的字符串数据对象调用 `str1` ：

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

## <a name="cstringdataunlock"></a><a name="unlock"></a> CStringData：： Unlock

解锁关联的字符串对象的字符缓冲区。

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>备注

调用此函数可解锁字符串数据对象的字符缓冲区。 锁定缓冲区后，它是可共享的，并且可以进行引用计数。

> [!NOTE]
> 对的每个调用 `Lock` 必须通过对的相应调用进行匹配 `Unlock` 。

当开发人员必须确保不共享字符串数据时，可以使用锁定和解锁。 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)和[UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)方法演示了锁定的一个很好示例 `CSimpleStringT` 。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共享类](../../atl-mfc-shared/atl-mfc-shared-classes.md)
