---
description: 了解详细信息： uninitialized_object 类
title: uninitialized_object 类
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 4929de9e865492c9fb468f5fac336f67fb307efb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326385"
---
# <a name="uninitialized_object-class"></a>uninitialized_object 类

当使用未初始化的对象时引发的异常。

## <a name="syntax"></a>语法

```cpp
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[uninitialized_object 构造函数](#uninitialized_object)|初始化 `uninitialized_object` 类的新实例。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>要求

**标头：** amprt

**命名空间：** 并发

## <a name="uninitialized_object"></a><a name="uninitialized_object"></a> uninitialized_object

构造异常的新实例 `uninitialized_object` 。

### <a name="syntax"></a>语法

```cpp
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
对错误的说明。

### <a name="return-value"></a>返回值

`uninitialized_object`异常对象。

## <a name="see-also"></a>请参阅

[并发命名空间 (C++ AMP) ](concurrency-namespace-cpp-amp.md)
