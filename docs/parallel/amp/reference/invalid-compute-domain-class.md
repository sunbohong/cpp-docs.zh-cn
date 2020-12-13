---
description: 了解详细信息： invalid_compute_domain 类
title: invalid_compute_domain 类
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 7598180a12cacabcdb308c3924c84eb17ec90ed7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330002"
---
# <a name="invalid_compute_domain-class"></a>invalid_compute_domain 类

当运行时无法通过使用在 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) 调用站点指定的计算域启动内核时引发的异常。

## <a name="syntax"></a>语法

```cpp
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[invalid_compute_domain 构造函数](#ctor)|初始化 `invalid_compute_domain` 类的新实例。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>要求

**标头：** amprt

**命名空间：** 并发

## <a name="invalid_compute_domain"></a><a name="ctor"></a> invalid_compute_domain

初始化类的新实例。

### <a name="syntax"></a>语法

```cpp
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
对错误的说明。

### <a name="return-value"></a>返回值

类的实例 `invalid_compute_domain`

## <a name="see-also"></a>请参阅

[并发命名空间 (C++ AMP) ](concurrency-namespace-cpp-amp.md)
