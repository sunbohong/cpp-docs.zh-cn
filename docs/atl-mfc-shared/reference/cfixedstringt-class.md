---
description: 了解详细信息： CFixedStringT 类
title: CFixedStringT 类
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: a613716364318ced140709d2b33e9d9c4299af0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166827"
---
# <a name="cfixedstringt-class"></a>CFixedStringT 类

此类表示具有固定字符缓冲区的字符串对象。

## <a name="syntax"></a>语法

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>parameters

*StringType*<br/>
用作固定字符串对象的基类，可以是任何 `CStringT` 基于的类型。 一些示例包括 `CString` 、 `CStringA` 和 `CStringW` 。

*t_nChars*<br/>
缓冲区中存储的字符数。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CFixedStringT：： CFixedStringT](#cfixedstringt)|字符串对象的构造函数。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CFixedStringT：： operator =](#operator_eq)|将新值分配给 `CFixedStringT` 对象。|

## <a name="remarks"></a>备注

此类是基于的自定义字符串类的示例 `CStringT` 。 尽管类似，但实现中的两个类有所不同。 与之间的主要 `CFixedStringT` 差异 `CStringT` 是：

- 初始字符缓冲区作为对象的一部分分配，并且大小 *t_nChars*。 这使得 `CFixedString` 对象可以占用连续的内存块以提高性能。 但是，如果对象的内容 `CFixedStringT` 增长到 *t_nChars* 以上，则会动态分配缓冲区。

- 对象的字符缓冲区 `CFixedStringT` 始终 ( *t_nChars*) 的长度相同。 对象的缓冲区大小没有限制 `CStringT` 。

- 的内存管理器 `CFixedStringT` 是自定义的，因此不允许在两个或多个对象之间共享 [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) 对象 `CFixedStringT` 。 `CStringT` 对象没有此限制。

有关对字符串对象的自定义 `CFixedStringT` 和内存管理的详细信息，请参阅 [内存管理和 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>要求

**标头：** cstringt

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a> CFixedStringT：： CFixedStringT

构造 `CFixedStringT` 对象。

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>parameters

*pszSrc*<br/>
要复制到此对象中的以 null 值结束的字符串 `CFixedStringT` 。

*strSrc*<br/>
`CFixedStringT`要复制到此对象中的现有对象 `CFixedStringT` 。

*pStringMgr*<br/>
指向对象的内存管理器的指针 `CFixedStringT` 。 有关 `IAtlStringMgr` 和内存管理的详细信息 `CFixedStringT` ，请参阅 [内存管理和 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)。

### <a name="remarks"></a>备注

由于构造函数将输入数据复制到新分配的存储中，因此应注意到可能会导致内存异常。 其中一些构造函数充当转换函数。

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a> CFixedStringT：： operator =

`CFixedStringT`使用新数据重新初始化现有对象。

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>parameters

*pszSrc*<br/>
要复制到此对象中的以 null 值结束的字符串 `CFixedStringT` 。

*strSrc*<br/>
`CFixedStringT`要复制到此对象中的现有 `CFixedStringT` 。

### <a name="remarks"></a>备注

你应注意到，只要你使用赋值运算符，就可能会发生内存异常，因为通常会分配新存储来保存生成的 `CFixedStringT` 对象。

## <a name="see-also"></a>请参阅

[CStringT 类](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共享类](../../atl-mfc-shared/atl-mfc-shared-classes.md)
