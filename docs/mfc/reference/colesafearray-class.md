---
description: 了解详细信息： COleSafeArray 类
title: COleSafeArray 类
ms.date: 08/29/2019
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: 6c33f58f71167c492883a25b05fce6bb8fb09916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226696"
---
# <a name="colesafearray-class"></a>COleSafeArray 类

与任意类型和维度的数组一起使用的类。

## <a name="syntax"></a>语法

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[COleSafeArray：： COleSafeArray](#colesafearray)|构造 `COleSafeArray` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[COleSafeArray：： AccessData](#accessdata)|检索指向数组数据的指针。|
|[COleSafeArray：： AllocData](#allocdata)|为数组分配内存。|
|[COleSafeArray：： AllocDescriptor](#allocdescriptor)|为安全数组描述符分配内存。|
|[COleSafeArray：： Attach](#attach)|向对象提供对现有 `VARIANT` 数组的控制 `COleSafeArray` 。|
|[COleSafeArray：： Clear](#clear)|释放基础中的所有数据 `VARIANT` 。|
|[COleSafeArray：： Copy](#copy)|创建现有数组的副本。|
|[COleSafeArray：： Create](#create)|创建安全数组。|
|[COleSafeArray：： CreateOneDim](#createonedim)|创建一维 `COleSafeArray` 对象。|
|[COleSafeArray：:D estroy](#destroy)|销毁现有数组。|
|[COleSafeArray：:D estroyData](#destroydata)|销毁安全数组中的数据。|
|[COleSafeArray：:D estroyDescriptor](#destroydescriptor)|销毁安全数组的描述符。|
|[COleSafeArray：:D etach](#detach)|将变体数组与 `COleSafeArray` 对象分离 (以便不会将数据) 释放。|
|[COleSafeArray：： GetByteArray](#getbytearray)|将安全数组的内容复制到 [CByteArray](../../mfc/reference/cbytearray-class.md)中。|
|[COleSafeArray：： GetDim](#getdim)|返回数组中的维数。|
|[COleSafeArray：： GetElement](#getelement)|检索安全数组的单个元素。|
|[COleSafeArray：： GetElemSize](#getelemsize)|返回安全数组中一个元素的大小（以字节为单位）。|
|[COleSafeArray：： GetLBound](#getlbound)|返回安全数组的任何维度的下限。|
|[COleSafeArray：： GetOneDimSize](#getonedimsize)|返回一维对象中元素的数目 `COleSafeArray` 。|
|[COleSafeArray：： GetUBound](#getubound)|返回安全数组的任意维度的上限。|
|[COleSafeArray：： Lock](#lock)|递增数组的锁计数，并在数组说明符中放置一个指向数组数据的指针。|
|[COleSafeArray：:P trOfIndex](#ptrofindex)|返回一个指向索引元素的指针。|
|[COleSafeArray：:P utElement](#putelement)|将单个元素分配到数组。|
|[COleSafeArray：： Redim](#redim)|更改安全数组的最右) 绑定 (最小有效。|
|[COleSafeArray：： ResizeOneDim](#resizeonedim)|更改一维对象中元素的数目 `COleSafeArray` 。|
|[COleSafeArray：： UnaccessData](#unaccessdata)|减小数组的锁计数，并使检索到的指针无效 `AccessData` 。|
|[COleSafeArray：： Unlock](#unlock)|减小数组的锁计数，以便可以对其进行释放或调整大小。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[COleSafeArray：： operator LPCVARIANT](#operator_lpcvariant)|访问对象的基础 `VARIANT` 结构 `COleSafeArray` 。|
|[COleSafeArray：： operator LPVARIANT](#operator_lpvariant)|访问对象的基础 `VARIANT` 结构 `COleSafeArray` 。|
|[COleSafeArray：： operator =](#operator_eq)|将值复制到 `COleSafeArray` (`SAFEARRAY` 、 `VARIANT` 、 `COleVariant` 或 `COleSafeArray` 数组) 的对象。|
|[COleSafeArray：： operator = =](#operator_eq_eq)|将两个变体 `SAFEARRAY` 数组 `VARIANT`)  (、、 `COleVariant` 或 `COleSafeArray` 数组进行比较。|
|[COleSafeArray：： operator &lt;&lt;](#operator_lt_lt)|将对象的内容输出 `COleSafeArray` 到转储上下文。|

## <a name="remarks"></a>备注

`COleSafeArray` 派生自 OLE `VARIANT` 结构。 OLE `SAFEARRAY` 成员函数通过提供 `COleSafeArray` ，还提供一组专门为一维字节数组设计的成员函数。

## <a name="inheritance-hierarchy"></a>继承层次结构

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>要求

**标头：** afxdisp.h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a> COleSafeArray：： AccessData

检索指向数组数据的指针。

```cpp
void AccessData(void** ppvData);
```

### <a name="parameters"></a>parameters

*ppvData*<br/>
指向数组数据的指针的指针。

### <a name="remarks"></a>备注

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a> COleSafeArray：： AllocData

为安全数组分配内存。

```cpp
void AllocData();
```

### <a name="remarks"></a>备注

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a> COleSafeArray：： AllocDescriptor

为安全数组的描述符分配内存。

```cpp
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>parameters

*dwDims*<br/>
安全数组中的维度数。

### <a name="remarks"></a>备注

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearrayattach"></a><a name="attach"></a> COleSafeArray：： Attach

将现有数组中的数据控件赋 `VARIANT` 给 `COleSafeArray` 对象。

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>parameters

*varSrc*<br/>
`VARIANT` 对象。 *VarSrc* 参数必须具有 VARTYPE [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)。

### <a name="remarks"></a>备注

源 `VARIANT` 的类型设置为 VT_EMPTY。 此函数清除当前数组数据（如果有）。

### <a name="example"></a>示例

  请参阅 [COleSafeArray：： AccessData](#accessdata)的示例。

## <a name="colesafearrayclear"></a><a name="clear"></a> COleSafeArray：： Clear

清除安全数组。

```cpp
void Clear();
```

### <a name="remarks"></a>备注

此函数通过将 `VARTYPE` 对象的设置为 VT_EMPTY 来清除安全数组。 将释放当前内容并释放数组。

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a> COleSafeArray：： COleSafeArray

构造 `COleSafeArray` 对象。

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>parameters

*saSrc*<br/>
`COleSafeArray` `SAFEARRAY` 要复制到新对象的现有对象 `COleSafeArray` 。

*vtSrc*<br/>
新对象的 VARTYPE `COleSafeArray` 。

*psaSrc*<br/>
指向 `SAFEARRAY` 要复制到新对象的的指针 `COleSafeArray` 。

*varSrc*<br/>
`VARIANT` `COleVariant` 要复制到新对象的现有或对象 `COleSafeArray` 。

*.Psrc*<br/>
指向要 `VARIANT` 复制到新对象中的对象的指针 `COleSafeArray` 。

### <a name="remarks"></a>备注

所有这些构造函数都创建新 `COleSafeArray` 对象。 如果没有参数， `COleSafeArray` 则 (VT_EMPTY) 中创建一个空对象。 如果 `COleSafeArray` 是从另一个数组（其 VARTYPE 隐式识别） (`COleSafeArray` 、 `COleVariant` 或) 进行复制 `VARIANT` ，则保留源数组的 VARTYPE 并且无需指定。 如果 `COleSafeArray` 是从其 vartype 未知的其他数组复制 (`SAFEARRAY`) ，则必须在 *vtSrc* 参数中指定 vartype。

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearraycopy"></a><a name="copy"></a> COleSafeArray：： Copy

创建现有安全数组的副本。

```cpp
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>parameters

*ppsa*<br/>
指向要返回新数组说明符的位置的指针。

### <a name="remarks"></a>备注

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearraycreate"></a><a name="create"></a> COleSafeArray：： Create

分配并初始化数组的数据。

```cpp
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>parameters

*vtSrc*<br/>
数组的基类型 (即，数组的每个元素的 VARTYPE) 。 VARTYPE 限制为变量类型的子集。 不能设置 VT_ARRAY 和 VT_BYREF 标志。 VT_EMPTY 和 VT_NULL 不是数组的有效基类型。 所有其他类型都是合法的。

*dwDims*<br/>
数组中的维度数。 这可以在通过 [Redim](#redim)创建数组后进行更改。

*rgElements*<br/>
指向数组中每个维度的元素数的数组的指针。

*rgsabounds*<br/>
指向边界向量的指针 (每个要为数组分配的维度) 。

### <a name="remarks"></a>备注

此函数将清除当前数组数据（如有必要）。 出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a> COleSafeArray：： CreateOneDim

创建新的一维 `COleSafeArray` 对象。

```cpp
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>parameters

*vtSrc*<br/>
数组的基类型 (即，数组的每个元素的 VARTYPE) 。

*dwElements*<br/>
数组中元素的数目。 这可以在用 [ResizeOneDim](#resizeonedim)创建数组后进行更改。

*pvSrcData*<br/>
指向要复制到数组中的数据的指针。

*nLBound*<br/>
数组的下限。

### <a name="remarks"></a>备注

如果指针 *pvSrcData* 不为 NULL，则函数为数组分配和初始化数据，并复制指定的数据。

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a> COleSafeArray：:D estroy

销毁数组中现有的数组描述符和所有数据。

```cpp
void Destroy();
```

### <a name="remarks"></a>备注

如果对象存储在数组中，则释放每个对象。 出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a> COleSafeArray：:D estroyData

销毁安全数组中的所有数据。

```cpp
void DestroyData();
```

### <a name="remarks"></a>备注

如果对象存储在数组中，则释放每个对象。 出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a> COleSafeArray：:D estroyDescriptor

销毁安全数组的描述符。

```cpp
void DestroyDescriptor();
```

### <a name="remarks"></a>备注

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearraydetach"></a><a name="detach"></a> COleSafeArray：:D etach

将 `VARIANT` 数据与对象分离 `COleSafeArray` 。

```
VARIANT Detach();
```

### <a name="return-value"></a>返回值

`VARIANT`对象中的基础值 `COleSafeArray` 。

### <a name="remarks"></a>备注

此函数通过将对象的 VARTYPE 设置为 VT_EMPTY 来分离安全数组中的数据。 调用方负责通过调用 Windows 函数 [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)释放数组。

出现错误时，函数将引发 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

  请参阅 [COleSafeArray：:P utelement](#putelement)的示例。

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a> COleSafeArray：： GetByteArray

将安全数组的内容复制到中 `CByteArray` 。

```cpp
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>parameters

*bytes*<br/>
对 [CByteArray](../../mfc/reference/cbytearray-class.md) 对象的引用。

## <a name="colesafearraygetdim"></a><a name="getdim"></a> COleSafeArray：： GetDim

返回对象中的维度数 `COleSafeArray` 。

```
DWORD GetDim();
```

### <a name="return-value"></a>返回值

安全数组中的维度数。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a> COleSafeArray：： GetElement

检索安全数组的单个元素。

```cpp
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>parameters

*rgIndices*<br/>
指向数组的每个维度的索引数组的指针。

*pvData*<br/>
指向要放置数组元素的位置的指针。

### <a name="remarks"></a>备注

此函数自动调用 windows 函数 `SafeArrayLock` ，以及在 `SafeArrayUnlock` 检索元素之前和之后。 如果数据元素是字符串、对象或变量，则函数以正确的方式复制元素。 参数 *pvData* 应指向足够大的缓冲区，以包含元素。

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a> COleSafeArray：： GetElemSize

检索对象中元素的大小 `COleSafeArray` 。

```
DWORD GetElemSize();
```

### <a name="return-value"></a>返回值

安全数组元素的大小（以字节为单位）。

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a> COleSafeArray：： GetLBound

返回对象的任何维度的下限 `COleSafeArray` 。

```cpp
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>parameters

*dwDim*<br/>
要获取其下限的数组维度。

*pLBound*<br/>
指向要返回下限的位置的指针。

### <a name="remarks"></a>备注

出现错误时，函数将引发 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a> COleSafeArray：： GetOneDimSize

返回一维对象中元素的数目 `COleSafeArray` 。

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>返回值

一维安全数组中的元素数。

### <a name="example"></a>示例

  请参阅 [COleSafeArray：： CreateOneDim](#createonedim)的示例。

## <a name="colesafearraygetubound"></a><a name="getubound"></a> COleSafeArray：： GetUBound

返回安全数组的任意维度的上限。

```cpp
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>parameters

*dwDim*<br/>
要获取其上限的数组维度。

*pUBound*<br/>
指向要返回上限的位置的指针。

### <a name="remarks"></a>备注

出现错误时，函数将引发 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a> COleSafeArray：： Lock

递增数组的锁计数，并在数组说明符中放置一个指向数组数据的指针。

```cpp
void Lock();
```

### <a name="remarks"></a>备注

出现错误时，将引发 [COleException](../../mfc/reference/coleexception-class.md)。

在调用之前，数组说明符中的指针是有效的 `Unlock` 。 对的调用 `Lock` 可以嵌套; 需要相等的调用数 `Unlock` 。

在锁定数组时，无法将其删除。

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a> COleSafeArray：： operator LPCVARIANT

调用此强制转换运算符可访问 `VARIANT` 此对象的基础结构 `COleSafeArray` 。

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a> COleSafeArray：： operator LPVARIANT

调用此强制转换运算符可访问 `VARIANT` 此对象的基础结构 `COleSafeArray` 。

```
operator LPVARIANT();
```

### <a name="remarks"></a>备注

请注意，更改 `VARIANT` 此函数所返回的指针所访问的结构中的值将更改此对象的值 `COleSafeArray` 。

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a> COleSafeArray：： operator =

这些重载赋值运算符将源值复制到此 `COleSafeArray` 对象中。

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>备注

下面是每个运算符的简要说明：

- **operator = (** *saSrc* **)** 将现有 `COleSafeArray` 对象复制到此对象中。

- **operator = (** *varSrc* **)** 将现有 `VARIANT` 或 `COleVariant` 数组复制到此对象中。

- **operator = (** *.Psrc* **)** 将 `VARIANT` *.psrc* 访问的数组对象复制到此对象中。

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a> COleSafeArray：： operator = =

此运算符将两个数组 `SAFEARRAY`)  (、 `VARIANT` 、或数组进行比较， `COleVariant` 如果相等，则 `COleSafeArray` 返回非零值; 否则返回0。

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>备注

如果两个数组的维数相等，每个维度的大小相等，且元素值相等，则这两个数组相等。

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a> COleSafeArray：： operator &lt;&lt;

`COleSafeArray`插入 ( # A2) 运算符支持将对象转储和存储 `COleSafeArray` 到存档的诊断。

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a> COleSafeArray：:P trOfIndex

返回一个指向索引值指定的元素的指针。

```cpp
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>parameters

*rgIndices*<br/>
标识数组元素的索引值的数组。 必须指定元素的所有索引。

*ppvData*<br/>
返回时，指针指向由 *rgIndices* 中的值标识的元素。

## <a name="colesafearrayputelement"></a><a name="putelement"></a> COleSafeArray：:P utElement

将单个元素分配到数组。

```cpp
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>parameters

*rgIndices*<br/>
指向数组的每个维度的索引数组的指针。

*pvData*<br/>
指向要分配给数组的数据的指针。 VT_DISPATCH、VT_UNKNOWN 和 VT_BSTR 变体类型是指针，并且不需要其他级别的间接寻址。

### <a name="remarks"></a>备注

此函数在赋值元素前后自动调用 Windows 函数 [SafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) 和 [SafeArrayUnlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) 。 如果数据元素是字符串、对象或变量，则函数将正确复制它，而如果现有元素是字符串、对象或变量，则将正确清除它。

请注意，你可以在一个数组上拥有多个锁，以便在数组被其他操作锁定时可以将元素放入该数组。

出现错误时，函数将引发 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 或 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a> COleSafeArray：： Redim

更改安全数组的最右) 绑定 (最小有效。

```cpp
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>parameters

*psaboundNew*<br/>
指向新的安全数组绑定结构的指针，该结构包含绑定的新数组。 仅可更改数组的最小有效维度。

### <a name="remarks"></a>备注

出现错误时，函数将引发 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a> COleSafeArray：： ResizeOneDim

更改一维对象中元素的数目 `COleSafeArray` 。

```cpp
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>parameters

*dwElements*<br/>
一维安全数组中的元素数。

### <a name="remarks"></a>备注

出现错误时，函数将引发 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

  请参阅 [COleSafeArray：： CreateOneDim](#createonedim)的示例。

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a> COleSafeArray：： UnaccessData

减小数组的锁计数，并使检索到的指针无效 `AccessData` 。

```cpp
void UnaccessData();
```

### <a name="remarks"></a>备注

出现错误时，函数将引发 [COleException](../../mfc/reference/coleexception-class.md)。

### <a name="example"></a>示例

  请参阅 [COleSafeArray：： AccessData](#accessdata)的示例。

## <a name="colesafearrayunlock"></a><a name="unlock"></a> COleSafeArray：： Unlock

减小数组的锁计数，以便可以对其进行释放或调整大小。

```cpp
void Unlock();
```

### <a name="remarks"></a>备注

在对数组中的数据进行访问后，将调用此函数。 出现错误时，将引发 [COleException](../../mfc/reference/coleexception-class.md)。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[COleVariant 类](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset 类](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase 类](../../mfc/reference/cdatabase-class.md)<br/>
