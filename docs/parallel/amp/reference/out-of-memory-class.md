---
description: 了解详细信息： out_of_memory 类
title: out_of_memory 类
ms.date: 11/04/2016
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
ms.openlocfilehash: bb7ba1db5be5921111b1fba2e12ea5cf6a5bea1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329926"
---
# <a name="out_of_memory-class"></a>out_of_memory 类

当某个方法因缺少系统或设备内存而失败时引发的异常。

## <a name="syntax"></a>语法

```cpp
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[out_of_memory 构造函数](#ctor)|初始化 `out_of_memory` 类的新实例。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>要求

**标头：** amprt

**命名空间：** 并发

## <a name="out_of_memory"></a><a name="ctor"></a> out_of_memory

初始化类的新实例。

### <a name="syntax"></a>语法

```cpp
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
对错误的说明。

### <a name="return-value"></a>返回值

`out_of_memory` 类的新实例。

## <a name="see-also"></a>请参阅

[并发命名空间 (C++ AMP) ](concurrency-namespace-cpp-amp.md)
