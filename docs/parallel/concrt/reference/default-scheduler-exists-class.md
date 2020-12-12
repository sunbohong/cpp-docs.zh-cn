---
description: 了解详细信息： default_scheduler_exists 类
title: default_scheduler_exists 类
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: 6921f7bd820271cf590707c2e56cefa9f576cefe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284845"
---
# <a name="default_scheduler_exists-class"></a>default_scheduler_exists 类

此类描述在进程内已存在默认计划程序的情况下调用 `Scheduler::SetDefaultSchedulerPolicy` 方法时引发的异常。

## <a name="syntax"></a>语法

```cpp
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|已重载。 构造 `default_scheduler_exists` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="default_scheduler_exists"></a><a name="ctor"></a> default_scheduler_exists

构造 `default_scheduler_exists` 对象。

```cpp
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
