---
description: 了解详细信息： CComSafeArray 类
title: CComSafeArray 类
ms.date: 05/06/2019
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
ms.openlocfilehash: e25719ffb9817595a1c1cc108a9d9ffc91459fe1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142304"
---
# <a name="ccomsafearray-class"></a>CComSafeArray 类

此类是结构的包装器 `SAFEARRAY` 。

## <a name="syntax"></a>语法

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在数组中的数据类型。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComSafeArray：： CComSafeArray](#ccomsafearray)|构造函数。|
|[CComSafeArray：： ~ CComSafeArray](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComSafeArray：： Add](#add)|将一个或多个元素（或 `SAFEARRAY` 结构）添加到 `CComSafeArray` 。|
|[CComSafeArray：： Attach](#attach)|将 `SAFEARRAY` 结构附加到 `CComSafeArray` 对象。|
|[CComSafeArray：： CopyFrom](#copyfrom)|将结构的内容复制 `SAFEARRAY` 到对象中 `CComSafeArray` 。|
|[CComSafeArray：： CopyTo](#copyto)|创建 `CComSafeArray` 对象的副本。|
|[CComSafeArray::Create](#create)|创建一个 `CComSafeArray` 对象。|
|[CComSafeArray::Destroy](#destroy)|销毁 `CComSafeArray` 对象。|
|[CComSafeArray：:D etach](#detach)|`SAFEARRAY`从 `CComSafeArray` 对象分离。|
|[CComSafeArray：： GetAt](#getat)|从一维数组中检索单个元素。|
|[CComSafeArray：： GetCount](#getcount)|返回数组中的元素数目。|
|[CComSafeArray：： GetDimensions](#getdimensions)|返回数组中的维数。|
|[CComSafeArray：： GetLowerBound](#getlowerbound)|返回数组给定维度的下限。|
|[CComSafeArray：： GetSafeArrayPtr](#getsafearrayptr)|返回 `m_psa` 数据成员的地址。|
|[CComSafeArray：： GetType](#gettype)|返回数组中存储的数据类型。|
|[CComSafeArray：： System.array.getupperbound](#getupperbound)|返回数组任意维度的上限。|
|[CComSafeArray：： IsSizable](#issizable)|测试是否可重设 `CComSafeArray` 对象的大小。|
|[CComSafeArray：： MultiDimGetAt](#multidimgetat)|从多维数组中检索单个元素。|
|[CComSafeArray：： MultiDimSetAt](#multidimsetat)|设置多维数组中元素的值。|
|[CComSafeArray：： Resize](#resize)|重设 `CComSafeArray` 对象的大小。|
|[CComSafeArray：： SetAt](#setat)|设置一维数组中元素的值。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CComSafeArray：： operator LPSAFEARRAY](#operator_lpsafearray)|将值强制转换为 `SAFEARRAY` 指针。|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|从数组中检索元素。|
|[CComSafeArray：： operator =](#operator_eq)|赋值运算符。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CComSafeArray：： m_psa](#m_psa)|此数据成员保存结构的地址 `SAFEARRAY` 。|

## <a name="remarks"></a>备注

`CComSafeArray` 为 [SAFEARRAY 数据类型](/windows/win32/api/oaidl/ns-oaidl-safearray) 类提供包装器，这使得创建和管理几乎所有支持 VARIANT 的类型的一维数组和多维数组更为重要。

`CComSafeArray` 可简化数组在进程之间的传递，此外还可以对照上限和下限检查数组索引值，从而提供额外的安全性。

`CComSafeArray` 的下限可以从任何用户定义值开始；但是，通过 C++ 访问的数组应该使用下限 0。 Visual Basic 等其他语言可以使用其他边界值（例如，-10 到 10）。

使用 [CComSafeArray::Create](#create) 可以创建 `CComSafeArray` 对象，使用 [CComSafeArray::Destroy](#destroy) 可将其删除。

`CComSafeArray` 可以包含以下 VARIANT 数据类型子集：

|VARTYPE|描述|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|字节|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|十进制指针|
|VT_VARIANT|变体指针|
|VT_CY|货币数据类型|

## <a name="requirements"></a>要求

**标头：** atlsafe.h

## <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

## <a name="ccomsafearrayadd"></a><a name="add"></a> CComSafeArray：： Add

将一个或多个元素（或 `SAFEARRAY` 结构）添加到 `CComSafeArray` 。

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>parameters

*psaSrc*<br/>
一个指向 `SAFEARRAY` 对象的指针。

*ulCount*<br/>
要添加到数组中的对象的数目。

*五*<br/>
指向一个或多个要添加到数组中的对象的指针。

*t*<br/>
对要添加到数组中的对象的引用。

*bCopy*<br/>
指示是否应创建数据的副本。 默认值为 TRUE。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

新的对象将追加到现有对象的末尾 `SAFEARRAY` 。 不支持将对象添加到多维 `SAFEARRAY` 对象。 添加现有对象数组时，两个数组都必须包含相同类型的元素。

当将类型为 BSTR 或 VARIANT 的元素添加到数组时，将会考虑 *bCopy* 标志。 如果为 TRUE，则默认值为 TRUE 可确保在将元素添加到数组时，为数据生成新的副本。

## <a name="ccomsafearrayattach"></a><a name="attach"></a> CComSafeArray：： Attach

将 `SAFEARRAY` 结构附加到 `CComSafeArray` 对象。

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>parameters

*psaSrc*<br/>
指向结构的指针 `SAFEARRAY` 。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

将 `SAFEARRAY` 结构附加到 `CComSafeArray` 对象，从而使现有 `CComSafeArray` 方法可用。

## <a name="ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a> CComSafeArray：： CComSafeArray

构造函数。

```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>parameters

*绑定*<br/>
`SAFEARRAYBOUND` 结构。

*ulCount*<br/>
数组中的元素数。

*lLBound*<br/>
下限值;也就是说，数组中第一个元素的索引。

*pBound*<br/>
指向结构的指针 `SAFEARRAYBOUND` 。

*uDims*<br/>
数组中维度的计数。

*saSrc*<br/>
对 `SAFEARRAY` 结构或对象的引用 `CComSafeArray` 。 在这两种情况下，构造函数都将使用此引用来制作数组的副本，因此构造后不引用数组。

*psaSrc*<br/>
指向结构的指针 `SAFEARRAY` 。 构造函数使用此地址创建数组的副本，因此在构造后不引用数组。

### <a name="remarks"></a>备注

创建一个 `CComSafeArray` 对象。

## <a name="ccomsafearrayccomsafearray"></a><a name="dtor"></a> CComSafeArray：： ~ CComSafeArray

析构函数。

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

## <a name="ccomsafearraycopyfrom"></a><a name="copyfrom"></a> CComSafeArray：： CopyFrom

将结构的内容复制 `SAFEARRAY` 到对象中 `CComSafeArray` 。

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>parameters

*ppArray*<br/>
指向要复制的的指针 `SAFEARRAY` 。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

此方法将的内容复制 `SAFEARRAY` 到当前对象中 `CComSafeArray` 。 将替换数组中的现有内容。

## <a name="ccomsafearraycopyto"></a><a name="copyto"></a> CComSafeArray：： CopyTo

创建 `CComSafeArray` 对象的副本。

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>parameters

*ppArray*<br/>
一个指针，指向要在其中创建新的位置 `SAFEARRAY` 。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

此方法将对象的内容复制 `CComSafeArray` 到结构中 `SAFEARRAY` 。

## <a name="ccomsafearraycreate"></a><a name="create"></a> CComSafeArray：： Create

创建一个 `CComSafeArray`。

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>parameters

*pBound*<br/>
一个指向 `SAFEARRAYBOUND` 对象的指针。

*uDims*<br/>
数组的维数。

*ulCount*<br/>
数组中的元素数。

*lLBound*<br/>
下限值;也就是说，数组中第一个元素的索引。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

`CComSafeArray`可以从现有 `SAFEARRAYBOUND` 结构和维度数创建对象，也可以通过指定数组中的元素数和下限来创建对象。 如果要从 c + + 访问数组，则下限应为0。 其他语言可能允许下限 (的其他值例如，Visual Basic 支持包含元素的数组，这些元素的范围为-10 到10，) 。

## <a name="ccomsafearraydestroy"></a><a name="destroy"></a> CComSafeArray：:D estroy

销毁 `CComSafeArray` 对象。

```
HRESULT Destroy();
```

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

销毁现有 `CComSafeArray` 对象及其包含的所有数据。

## <a name="ccomsafearraydetach"></a><a name="detach"></a> CComSafeArray：:D etach

`SAFEARRAY`从 `CComSafeArray` 对象分离。

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>返回值

返回一个指向对象的指针 `SAFEARRAY` 。

### <a name="remarks"></a>备注

此方法 `SAFEARRAY` 从对象分离对象 `CComSafeArray` 。

## <a name="ccomsafearraygetat"></a><a name="getat"></a> CComSafeArray：： GetAt

从一维数组中检索单个元素。

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>parameters

*lIndex*<br/>
要返回的数组中的值的索引号。

### <a name="return-value"></a>返回值

返回对所需数组元素的引用。

## <a name="ccomsafearraygetcount"></a><a name="getcount"></a> CComSafeArray：： GetCount

返回数组中的元素数目。

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>parameters

*uDim*<br/>
数组维度。

### <a name="return-value"></a>返回值

返回数组中的元素数目。

### <a name="remarks"></a>备注

与多维数组一起使用时，此方法将仅返回特定维度中的元素数。

## <a name="ccomsafearraygetdimensions"></a><a name="getdimensions"></a> CComSafeArray：： GetDimensions

返回数组中的维数。

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>返回值

返回数组中的维数。

## <a name="ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a> CComSafeArray：： GetLowerBound

返回数组给定维度的下限。

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>parameters

*uDim*<br/>
要获取其下限的数组维度。 如果省略，则默认值为0。

### <a name="return-value"></a>返回值

返回下限。

### <a name="remarks"></a>备注

如果下限为0，则表示一个类似于 C 的数组，其第一个元素是元素号0。 例如，如果发生错误，则此方法将 `AtlThrow` 使用 HRESULT （描述错误）调用。

## <a name="ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a> CComSafeArray：： GetSafeArrayPtr

返回 `m_psa` 数据成员的地址。

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>返回值

返回指向 [CComSafeArray：： m_psa](#m_psa) 数据成员的指针。

## <a name="ccomsafearraygettype"></a><a name="gettype"></a> CComSafeArray：： GetType

返回数组中存储的数据类型。

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>返回值

返回数组中存储的数据的类型，可以是以下类型之一：

|VARTYPE|描述|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|字节|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|十进制指针|
|VT_VARIANT|变体指针|
|VT_CY|货币数据类型|

## <a name="ccomsafearraygetupperbound"></a><a name="getupperbound"></a> CComSafeArray：： System.array.getupperbound

返回数组任意维度的上限。

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>parameters

*uDim*<br/>
要获取其上限的数组维度。 如果省略，则默认值为0。

### <a name="return-value"></a>返回值

返回上限。 此值为 "包含"，这是此维度的最大有效索引。

### <a name="remarks"></a>备注

例如，如果发生错误，则此方法将 `AtlThrow` 使用 HRESULT （描述错误）调用。

## <a name="ccomsafearrayissizable"></a><a name="issizable"></a> CComSafeArray：： IsSizable

测试是否可重设 `CComSafeArray` 对象的大小。

```
bool IsSizable() const;
```

### <a name="return-value"></a>返回值

如果 `CComSafeArray` 可以调整大小，则返回 TRUE; 否则返回 FALSE。

## <a name="ccomsafearraym_psa"></a><a name="m_psa"></a> CComSafeArray：： m_psa

保存所 `SAFEARRAY` 访问结构的地址。

```
LPSAFEARRAY m_psa;
```

## <a name="ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a> CComSafeArray：： MultiDimGetAt

从多维数组中检索单个元素。

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>parameters

*alIndex*<br/>
指向数组中每个维度的索引向量的指针。 最左端的 (最) 维度是 `alIndex[0]` 。

*t*<br/>
对返回的数据的引用。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

## <a name="ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a> CComSafeArray：： MultiDimSetAt

设置多维数组中元素的值。

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>parameters

*alIndex*<br/>
指向数组中每个维度的索引向量的指针。 最右边的 (最小) 维度是 `alIndex` [0]。

*T*<br/>
指定新元素的值。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

这是 [CComSafeArray：： SetAt](#setat)的多维版本。

## <a name="ccomsafearrayoperator-"></a><a name="operator_at"></a> CComSafeArray：： operator \[\]

从数组中检索元素。

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>parameters

*lIndex, nIndex*<br/>
数组中所需元素的索引号。

### <a name="return-value"></a>返回值

返回相应的数组元素。

### <a name="remarks"></a>备注

对 [CComSafeArray：： GetAt](#getat)执行类似的函数，但此运算符仅适用于一维数组。

## <a name="ccomsafearrayoperator-"></a><a name="operator_eq"></a> CComSafeArray：： operator =

赋值运算符。

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>parameters

*saSrc*<br/>
对 `CComSafeArray` 对象的引用。

*psaSrc*<br/>
一个指向 `SAFEARRAY` 对象的指针。

### <a name="return-value"></a>返回值

返回数组中存储的数据类型。

## <a name="ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a> CComSafeArray：： operator LPSAFEARRAY

将值强制转换为 `SAFEARRAY` 指针。

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>返回值

将值强制转换为 `SAFEARRAY` 指针。

## <a name="ccomsafearrayresize"></a><a name="resize"></a> CComSafeArray：： Resize

重设 `CComSafeArray` 对象的大小。

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>parameters

*pBound*<br/>
指向 `SAFEARRAYBOUND` 结构的指针，该结构包含有关数组的元素数和下限的信息。

*ulCount*<br/>
已调整大小的数组中请求的对象数。

*lLBound*<br/>
下限。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

此方法仅调整最右侧维度的大小。 它不会调整返回为 FALSE 的数组的大小 `IsResizable` 。

## <a name="ccomsafearraysetat"></a><a name="setat"></a> CComSafeArray：： SetAt

设置一维数组中元素的值。

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>parameters

*lIndex*<br/>
要设置的数组元素的索引号。

*t*<br/>
已指定元素的新值。

*bCopy*<br/>
指示是否应创建数据的副本。 默认值为 TRUE。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

当将类型为 BSTR 或 VARIANT 的元素添加到数组时，将会考虑 *bCopy* 标志。 如果为 TRUE，则默认值为 TRUE 可确保在将元素添加到数组时，为数据生成新的副本。

## <a name="see-also"></a>请参阅

[SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[CComSafeArray::Create](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[类概述](../../atl/atl-class-overview.md)
