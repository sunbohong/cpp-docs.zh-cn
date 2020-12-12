---
description: 了解详细信息： Platform：： Guid 值类
title: Platform::Guid 值类
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 4c2ffc5096e6b40266fef0934acc562edf721c24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195185"
---
# <a name="platformguid-value-class"></a>Platform::Guid 值类

表示 Windows 运行时类型系统中的 [GUID] (/windows/win32/api/guiddef/ns-guiddef-guid 类型。

## <a name="syntax"></a>语法

```cpp
public value struct Guid
```

### <a name="members"></a>成员

`Platform::Guid` 具有 `Equals()` `GetHashCode()` `ToString()` 派生自 [Platform：： Object 类](../cppcx/platform-object-class.md)的、和方法，以及 `GetTypeCode()` 派生自 [platform：： Type 类](../cppcx/platform-type-class.md)的方法。 `Platform::Guid` 还具有下列成员。

|成员|描述|
|------------|-----------------|
|[Guid.empty](#ctor)|初始化 `Platform::Guid` 的新实例。|
|[operator = =](#operator-equality)|等于运算符。|
|[operator！ =](#operator-inequality)|不等于运算符。|
|[操作员&lt;](#operator-less)|小于运算符。|
|[运算符 ( # B1 ](#operator-call)|将 `Platform::Guid` 转换为 `GUID`。|

### <a name="remarks"></a>备注

若要生成新的 `Platform::Guid` ，请使用 [Windows：： Foundation：： GuidHelper：： CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid) 静态方法。

### <a name="requirements"></a>要求

**支持的最低客户端：** Windows 8

**支持的最低服务器：** Windows Server 2012

**命名空间：** Platform

**Metadata：** platform.string

## <a name="guidguid-constructors"></a><a name="ctor"></a> Guid：： Guid 构造函数

初始化 `Platform::Guid` 的新实例。

### <a name="syntax"></a>语法

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>parameters

*的*<br/>
的前4个字节 `GUID` 。

*b*<br/>
的下2个字节 `GUID` 。

*c*<br/>
的下2个字节 `GUID` 。

*d*<br/>
`GUID` 的下一个字节。

*e*<br/>
`GUID` 的下一个字节。

*f*<br/>
`GUID` 的下一个字节。

*g*<br/>
`GUID` 的下一个字节。

*h*<br/>
`GUID` 的下一个字节。

*i*<br/>
`GUID` 的下一个字节。

*j*<br/>
`GUID` 的下一个字节。

*k*<br/>
`GUID` 的下一个字节。

*m*<br/>
`GUID`以[GUID 结构](/windows/win32/api/guiddef/ns-guiddef-guid)形式表示的。

*n*<br/>
的剩余8个字节 `GUID` 。

## <a name="guidoperator-operator"></a><a name="operator-equality"></a> Guid：： operator = = 运算符

比较两个 `Platform::Guid` 实例是否相等。

### <a name="syntax"></a>语法

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>parameters

*guid1*<br/>
要比较的第一个 `Platform::Guid`。

*guid2*<br/>
要比较的第二个 `Platform::Guid`。

### <a name="return-value"></a>返回值

如果两个实例相等，则为 True `Platform::Guid` 。

### <a name="remarks"></a>备注

首选使用 `==` 运算符，而不是 [Windows：： Foundation：： GuidHelper：： Equals](/uwp/api/windows.foundation.guidhelper.equals) 静态方法。

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a> Guid：： operator！ = 运算符

比较两个 `Platform::Guid` 实例是否不相等。

### <a name="syntax"></a>语法

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>parameters

*guid1*<br/>
要比较的第一个 `Platform::Guid`。

*guid2*<br/>
要比较的第二个 `Platform::Guid`。

### <a name="return-value"></a>返回值

如果两个实例不相等，则为 True `Platform::Guid` 。

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a> Guid：： operator &lt; 运算符

比较两个 `Platform::Guid` 实例以进行排序。

### <a name="syntax"></a>语法

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>parameters

*guid1*<br/>
要比较的第一个 `Platform::Guid`。

*guid2*<br/>
要比较的第二个 `Platform::Guid`。

### <a name="return-value"></a>返回值

如果在 *guid2* 之前对 *guid1* 进行排序，则为 True。 将每个排序 `Platform::Guid` 视为 4 32 位无符号值数组后，将字典排序。 这并不是 SQL Server 或 .NET Framework 使用的顺序，也不是按字符串表示形式按字典排序的顺序。

提供此运算符是为了使 `Guid` c + + 标准库更容易地使用对象。

## <a name="guidoperator-operator"></a><a name="operator-call"></a> Guid：： operator ( # A1 运算符

将隐式转换 `Platform::Guid` 为 [GUID 结构](/windows/win32/api/guiddef/ns-guiddef-guid)。

### <a name="syntax"></a>语法

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>返回值

[GUID 结构](/windows/win32/api/guiddef/ns-guiddef-guid)。

## <a name="see-also"></a>请参阅

[Platform 命名空间](../cppcx/platform-namespace-c-cx.md)
