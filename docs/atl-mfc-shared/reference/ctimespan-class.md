---
title: CTimeSpan 类
ms.date: 10/18/2018
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
ms.openlocfilehash: 0c13aa0d8f6c46db3b018283ab2a408a3f9531e1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832017"
---
# <a name="ctimespan-class"></a>CTimeSpan 类

时间长度，在内部存储为时间跨度中的秒数。

## <a name="syntax"></a>语法

```
class CTimeSpan
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|说明|
|----------|-----------------|
|[CTimeSpan::CTimeSpan](#ctimespan)|`CTimeSpan`以多种方式构造对象。|

### <a name="public-methods"></a>公共方法

|“属性”|说明|
|----------|-----------------|
|[CTimeSpan：： Format](#format)|将转换为 `CTimeSpan` 带格式的字符串。|
|[CTimeSpan::GetDays](#getdays)|返回一个值，该值表示此中的完整天数 `CTimeSpan` 。|
|[CTimeSpan：： GetHours](#gethours)|返回一个值，该值表示当天 (-23 到 23) 中的小时数。|
|[CTimeSpan：： GetMinutes](#getminutes)|返回一个值，该值表示当前小时 (-59 到 59) 中的分钟数。|
|[CTimeSpan：： GetSeconds](#getseconds)|返回一个值，该值表示当前分钟 (-59 到 59) 中的秒数。|
|[CTimeSpan::GetTimeSpan](#gettimespan)|返回对象的值 `CTimeSpan` 。|
|[CTimeSpan::GetTotalHours](#gettotalhours)|返回一个值，该值表示此中的总小时数 `CTimeSpan` 。|
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|返回一个值，该值表示此中的完整分钟数 `CTimeSpan` 。|
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|返回一个值，该值表示此中完成的总秒数 `CTimeSpan` 。|
|[CTimeSpan::Serialize64](#serialize64)|在存档中序列化数据。|

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator +-](#operator_add_-)|添加和减少 `CTimeSpan` 对象。|
|[operator + =-=](#operator_add_eq_-_eq)|在 `CTimeSpan` 此向和向中添加对象 `CTimeSpan` 。|
|[operator = = < 等。](#ctimespan_comparison_operators)|比较两个相对时间值。|

## <a name="remarks"></a>注解

`CTimeSpan` 没有基类。

`CTimeSpan` 函数将秒转换为不同的天数、小时数、分钟数和秒数的组合。

`CTimeSpan`对象存储在 **__time64_t**结构中，该结构是8个字节。

伴生类 [CTime](../../atl-mfc-shared/reference/ctime-class.md)表示绝对时间。

`CTime`和 `CTimeSpan` 类不用于派生。 由于没有虚函数， `CTime` 因此和对象的大小 `CTimeSpan` 正好为8个字节。 大多数成员函数是内联的。

有关使用的详细信息 `CTimeSpan` ，请参阅文章[日期和时间](../../atl-mfc-shared/date-and-time.md)和*运行时库参考*中的[时间管理](../../c-runtime-library/time-management.md)。

## <a name="requirements"></a>要求

**标头：** atltime

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a> CTimeSpan 比较运算符

比较运算符。

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>参数

*格*<br/>
要比较的对象。

### <a name="return-value"></a>返回值

这些运算符比较了两个相对时间值。 如果条件为 true，则返回 TRUE;否则为 FALSE。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a> CTimeSpan::CTimeSpan

`CTimeSpan`以多种方式构造对象。

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(
    LONG lDays,
    int nHours,
    int nMins,
    int nSecs) throw();
```

### <a name="parameters"></a>参数

*timeSpanSrc*<br/>
`CTimeSpan`已存在的对象。

*time*<br/>
一个 **__time64_t** 时间值，该值为时间跨度中的秒数。

*lDays*、 *nHours*、 *nMins*、 *nSecs*<br/>
分别为天、小时、分钟和秒。

### <a name="remarks"></a>注解

所有这些构造函数创建一个 `CTimeSpan` 使用指定的相对时间初始化的新对象。 每个构造函数如下所述：

- `CTimeSpan( );` 构造未初始化的 `CTimeSpan` 对象。

- `CTimeSpan( const CTimeSpan& );``CTimeSpan`从另一个值构造对象 `CTimeSpan` 。

- `CTimeSpan( __time64_t );``CTimeSpan`从 **__time64_t**类型构造对象。

- `CTimeSpan( LONG, int, int, int );` 构造一个 `CTimeSpan` 对象，其中每个组件都受限于以下范围：

   |组件|范围|
   |---------------|-----------|
   |*lDays*|0-25000 (大约) |
   |*nHours*|0-23|
   |*nMins*|0-59|
   |*nSecs*|0-59|

请注意，如果一个或多个时间部分组件超出范围，则 Microsoft 基础类库的调试版本将断言。 在调用之前验证参数是您的责任。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a> CTimeSpan：： Format

生成与此相对应的格式化字符串 `CTimeSpan` 。

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>参数

*pFormat*、 *pszFormat*<br/>
格式字符串类似于格式设置 `printf` 字符串。 格式设置代码（前面以百分号 (`%`) 符号）将替换为相应的 `CTimeSpan` 组件。 格式字符串中的其他字符将按原样复制到返回的字符串中。 下面列出了的格式设置代码的值和含义 `Format` ：

- **% D** 此项中的总天数 `CTimeSpan`

- **% H** 当天的小时

- **% M** 当前小时内的分钟数

- **% S** 当前分钟中的秒数

- **%%** 百分号

*nID*<br/>
标识此格式的字符串的 ID。

### <a name="return-value"></a>返回值

一个 `CString` 包含格式化时间的对象。

### <a name="remarks"></a>注解

如果代码不在上面的列表中，则库的调试版本将检查格式设置代码和断言。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a> CTimeSpan::GetDays

返回一个值，该值表示此中的完整天数 `CTimeSpan` 。

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>返回值

返回时间范围内的完整24小时数。 如果时间跨度为负数，此值可能为负数。

### <a name="remarks"></a>注解

请注意，夏令时可能会导致 `GetDays` 返回可能令人惊讶的结果。 例如，当 DST 生效时，将 `GetDays` 报告4月1日到5月1日之间的天数，而不是30，因为4月的一天缩短了一小时，因此不计为完整的一天。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a> CTimeSpan：： GetHours

返回一个值，该值表示当天 (-23 到 23) 中的小时数。

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>返回值

返回当前日期中的小时数。 范围为-23 到23。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a> CTimeSpan：： GetMinutes

返回一个值，该值表示当前小时 (-59 到 59) 中的分钟数。

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>返回值

返回当前小时中的分钟数。 范围为-59 到59。

### <a name="example"></a>示例

请参阅 [GetHours](#gethours)的示例。

## <a name="ctimespangetseconds"></a><a name="getseconds"></a> CTimeSpan：： GetSeconds

返回一个值，该值表示当前分钟 (-59 到 59) 中的秒数。

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>返回值

返回当前分钟中的秒数。 范围为-59 到59。

### <a name="example"></a>示例

请参阅 [GetHours](#gethours)的示例。

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a> CTimeSpan::GetTimeSpan

返回对象的值 `CTimeSpan` 。

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>返回值

返回对象的当前值 `CTimeSpan` 。

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a> CTimeSpan::GetTotalHours

返回一个值，该值表示此中的总小时数 `CTimeSpan` 。

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>返回值

返回此中的总小时数 `CTimeSpan` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a> CTimeSpan::GetTotalMinutes

返回一个值，该值表示此中的完整分钟数 `CTimeSpan` 。

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>返回值

返回此中完成的总分钟数 `CTimeSpan` 。

### <a name="example"></a>示例

请参阅 [GetTotalHours](#gettotalhours)的示例。

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a> CTimeSpan::GetTotalSeconds

返回一个值，该值表示此中完成的总秒数 `CTimeSpan` 。

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>返回值

返回此中完成的总秒数 `CTimeSpan` 。

### <a name="example"></a>示例

请参阅 [GetTotalHours](#gettotalhours)的示例。

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a> CTimeSpan：： operator +，-

添加和减少 `CTimeSpan` 对象。

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>参数

*格*<br/>
要添加到对象的值 `CTimeSpan` 。

### <a name="return-value"></a>返回值

`CTimeSpan`表示操作结果的对象。

### <a name="remarks"></a>注解

利用这两个运算符，您可以在 `CTimeSpan` 对象之间添加和减少对象。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a> CTimeSpan：： operator + =，-=

在 `CTimeSpan` 此向和向中添加对象 `CTimeSpan` 。

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>参数

*格*<br/>
要添加到对象的值 `CTimeSpan` 。

### <a name="return-value"></a>返回值

已更新的 `CTimeSpan` 对象。

### <a name="remarks"></a>注解

通过这些运算符，可以在此添加和减少 `CTimeSpan` 对象 `CTimeSpan` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a> CTimeSpan::Serialize64

> [!NOTE]
> 此方法仅在 MFC 项目中可用。

从存档中将与成员变量关联的数据序列化。

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>参数

*ar*<br/>
`CArchive`要更新的对象。

### <a name="return-value"></a>返回值

已更新的 `CArchive` 对象。

## <a name="see-also"></a>另请参阅

[asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共享类](../../atl-mfc-shared/atl-mfc-shared-classes.md)
