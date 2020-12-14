---
description: 了解详细信息： scheduler_resource_allocation_error 类
title: scheduler_resource_allocation_error 类
ms.date: 11/04/2016
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
ms.openlocfilehash: 50f84cbf76d30a415e2393797baa7d6cfa1e89f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188724"
---
# <a name="scheduler_resource_allocation_error-class"></a>scheduler_resource_allocation_error 类

此类描述因未能在并发运行时中获取关键资源而引发的异常。

## <a name="syntax"></a>语法

```cpp
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|已重载。 构造 `scheduler_resource_allocation_error` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[get_error_code](#get_error_code)|返回导致异常的错误代码。|

## <a name="remarks"></a>备注

当从并发运行时中对操作系统的调用失败时，通常会引发此异常。 通常从调用 Win32 方法 `GetLastError` 返回的错误代码将转换为类型 `HRESULT` 的值，并且可以使用 `get_error_code` 方法检索。

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="get_error_code"></a><a name="get_error_code"></a> get_error_code

返回导致异常的错误代码。

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>返回值

`HRESULT`导致异常的错误的值。

## <a name="scheduler_resource_allocation_error"></a><a name="ctor"></a> scheduler_resource_allocation_error

构造 `scheduler_resource_allocation_error` 对象。

```cpp
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

*_Hresult*<br/>
`HRESULT`导致异常的错误的值。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
