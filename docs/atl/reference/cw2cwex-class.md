---
description: 了解详细信息： CW2CWEX 类
title: CW2CWEX 类
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 769dcedf1a9dc15129b09e3305330de33242562e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140226"
---
# <a name="cw2cwex-class"></a>CW2CWEX 类

此类由字符串转换宏 CW2CTEX 和 CT2CWEX 以及 typedef CW2W 使用。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>parameters

*t_nBufferLength*<br/>
在转换过程中使用的缓冲区大小。 默认长度为128个字节。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|构造函数。|
|[CW2CWEX：： ~ CW2CWEX](#dtor)|析构函数。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CW2CWEX：： operator LPCWSTR](#operator_lpcwstr)|转换运算符。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CW2CWEX：： m_psz](#m_psz)|存储源字符串的数据成员。|

## <a name="remarks"></a>备注

除非需要额外的功能，否则请在代码中使用 CW2CTEX、CT2CWEX 或 CW2W。

此类可安全地在循环中使用，不会溢出堆栈。 默认情况下，ATL 转换类和宏将当前线程的 ANSI 代码页用于转换。

以下宏基于此类：

- CW2CTEX

- CT2CWEX

以下 typedef 基于此类：

- CW2W

有关这些文本转换宏的讨论，请参阅 [ATL 和 MFC 字符串转换宏](string-conversion-macros.md)。

## <a name="example"></a>示例

有关使用这些字符串转换宏的示例，请参阅 [ATL 和 MFC 字符串转换宏](string-conversion-macros.md) 。

## <a name="requirements"></a>要求

**标头：** atlconv。h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a> CW2CWEX::CW2CWEX

构造函数。

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>parameters

*psz*<br/>
要转换的文本字符串。

*nCodePage*<br/>
代码页。 此类中未使用。

### <a name="remarks"></a>备注

分配在转换过程中使用的缓冲区。

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a> CW2CWEX：： ~ CW2CWEX

析构函数。

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>备注

释放已分配的缓冲区。

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a> CW2CWEX：： m_psz

存储源字符串的数据成员。

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a> CW2CWEX：： operator LPCWSTR

转换运算符。

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>返回值

以 LPCWSTR 类型返回文本字符串。

## <a name="see-also"></a>请参阅

[CA2AEX 类](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX 类](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX 类](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX 类](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEX 类](../../atl/reference/cw2wex-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
