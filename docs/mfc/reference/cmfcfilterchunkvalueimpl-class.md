---
description: 了解详细信息： CMFCFilterChunkValueImpl 类
title: CMFCFilterChunkValueImpl 类
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: f2db7fdf6d6d24cb906b3190d34310e1f6724194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265462"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl 类

这是一个类，它可简化区块和属性值对逻辑。

## <a name="syntax"></a>语法

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCFilterChunkValueImpl：： ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Destructs 对象。|
|[CMFCFilterChunkValueImpl：： CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|构造对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCFilterChunkValueImpl：： Clear](#clear)|清除 ChunkValue。|
|[CMFCFilterChunkValueImpl：： CopyChunk](#copychunk)|将此区块复制到描述区块特征的结构。|
|[CMFCFilterChunkValueImpl：： CopyFrom](#copyfrom)|从另一个值初始化此区块值。|
|[CMFCFilterChunkValueImpl：： GetChunkGUID](#getchunkguid)|检索块 GUID GUID。|
|[CMFCFilterChunkValueImpl：： GetChunkPID](#getchunkpid)|检索块区 PID (属性 ID) 。|
|[CMFCFilterChunkValueImpl：： GetChunkType](#getchunktype)|获取块区类型。|
|[CMFCFilterChunkValueImpl：： GetString](#getstring)|检索字符串值。|
|[CMFCFilterChunkValueImpl：： GetValue](#getvalue)|检索值作为分配的 propvariant。|
|[CMFCFilterChunkValueImpl：： GetValueNoAlloc](#getvaluenoalloc)|) 值返回未分配 (内部值。|
|[CMFCFilterChunkValueImpl：： IsValid](#isvalid)|检查此属性值是否有效。|
|[CMFCFilterChunkValueImpl：： SetBoolValue](#setboolvalue)|已重载。 按键将属性设置为布尔值。|
|[CMFCFilterChunkValueImpl：： SetDwordValue](#setdwordvalue)|按键将属性设置为 DWORD 值。|
|[CMFCFilterChunkValueImpl：： SetFileTimeValue](#setfiletimevalue)|按键将属性设置为 filetime。|
|[CMFCFilterChunkValueImpl：： SetInt64Value](#setint64value)|按键将属性设置为 int64。|
|[CMFCFilterChunkValueImpl：： SetIntValue](#setintvalue)|按键将属性设置为 int。|
|[CMFCFilterChunkValueImpl：： SetLongValue](#setlongvalue)|按键将属性设置为 LONG。|
|[CMFCFilterChunkValueImpl：： SetSystemTimeValue](#setsystemtimevalue)|按键将属性设置为 SystemTime。|
|[CMFCFilterChunkValueImpl：： SetTextValue](#settextvalue)|按键将属性设置为 Unicode 字符串。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCFilterChunkValueImpl：： SetChunk](#setchunk)|用于设置块的公共属性的 helper 函数。|

## <a name="remarks"></a>备注

若要使用，只需创建正确类型的 CMFCFilterChunkValueImpl 类

示例：

CMFCFilterChunkValueImpl 块区;

hr = 块区。SetBoolValue (PKEY_IsAttachment、true) ;

或

hr = 块区。SetFileTimeValue (PKEY_ItemDate，ftLastModified) ;

## <a name="inheritance-hierarchy"></a>继承层次结构

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a> CMFCFilterChunkValueImpl：： Clear

清除 ChunkValue。

```cpp
void Clear();
```

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl：： CMFCFilterChunkValueImpl

构造对象。

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl：： ~ CMFCFilterChunkValueImpl

Destructs 对象。

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a> CMFCFilterChunkValueImpl：： CopyChunk

将此区块复制到描述区块特征的结构。

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>parameters

*pStatChunk*<br/>
指向描述块区特征的目标值的指针。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a> CMFCFilterChunkValueImpl：： CopyFrom

从另一个值初始化此区块值。

```cpp
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>parameters

*pValue*<br/>
指定要从中进行复制的源值。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a> CMFCFilterChunkValueImpl：： GetChunkGUID

检索块 GUID GUID。

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>返回值

对标识块区的 GUID 的引用。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a> CMFCFilterChunkValueImpl：： GetChunkPID

检索块区 PID (属性 ID) 。

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>返回值

一个包含属性 ID 的 DWORD 值。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a> CMFCFilterChunkValueImpl：： GetChunkType

检索块区类型。

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>返回值

CHUNKSTATE 枚举值，指定当前块区是文本类型属性还是值类型属性。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a> CMFCFilterChunkValueImpl：： GetString

检索字符串值。

```
CString &GetString();
```

### <a name="return-value"></a>返回值

包含区块值的字符串。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a> CMFCFilterChunkValueImpl：： GetValue

检索值作为分配的 propvariant。

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>parameters

*ppPropVariant*<br/>
当函数返回时，此参数包含区块值。

### <a name="return-value"></a>返回值

S_OK 如果已成功分配 PROPVARIANT 并且已成功将区块值复制到 *ppPropVariant*，则为;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a> CMFCFilterChunkValueImpl：： GetValueNoAlloc

返回 (内部值的未分配) 值。

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>返回值

返回当前区块值。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a> CMFCFilterChunkValueImpl：： IsValid

检查此属性值是否有效。

```
BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果当前区块值有效，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a> CMFCFilterChunkValueImpl：： SetBoolValue

已重载。 按键将属性设置为布尔值。

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*bVal*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a> CMFCFilterChunkValueImpl：： SetChunk

用于设置块的公共属性的 helper 函数。

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a> CMFCFilterChunkValueImpl：： SetDwordValue

按键将属性设置为 DWORD 值。

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*dwVal*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a> CMFCFilterChunkValueImpl：： SetFileTimeValue

按键将属性设置为 filetime。

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*dtVal*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a> CMFCFilterChunkValueImpl：： SetInt64Value

按键将属性设置为 int64。

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*nVal*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a> CMFCFilterChunkValueImpl：： SetIntValue

按键将属性设置为 int。

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*nVal*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a> CMFCFilterChunkValueImpl：： SetLongValue

按键将属性设置为 LONG。

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*lVal*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a> CMFCFilterChunkValueImpl：： SetSystemTimeValue

按键将属性设置为 SystemTime。

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*systemTime*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a> CMFCFilterChunkValueImpl：： SetTextValue

按键将属性设置为 Unicode 字符串。

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>parameters

*pkey*<br/>
指定属性键。

*pszValue*<br/>
指定要设置的区块值。

*chunkType*<br/>
标志指示此区块是否包含文本类型或值类型的属性。 标记值取自 CHUNKSTATE 枚举。

*locale*<br/>
与文本块关联的语言和子语言。 块区区域设置由文档索引器用来执行正确的文本断字。 如果块既不是文本类型，也不是值类型 VT_LPWSTR、VT_LPSTR 或 VT_BSTR，则忽略此字段。

*cwcLenSource*<br/>
当前块区派生的源文本的长度（以字符为字符）。 零值表示源文本和派生文本之间的逐字符对应。 非零值表示不存在此类直接对应的通信。

*cwcStartSource*<br/>
派生块源文本在源区块中开始的偏移量。

*chunkBreakType*<br/>
分隔上一个块与当前块区之间的分隔符的类型。 值来自 CHUNK_BREAKTYPE 枚举。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
