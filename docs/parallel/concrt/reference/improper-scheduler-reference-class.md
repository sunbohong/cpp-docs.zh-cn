---
description: 了解详细信息： improper_scheduler_reference 类
title: improper_scheduler_reference 类
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
ms.openlocfilehash: 4857418e14908b2d085d52249236d6395284b98a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334594"
---
# <a name="improper_scheduler_reference-class"></a>improper_scheduler_reference 类

此类描述从不属于该计划程序的上下文中，在正在关闭的 `Scheduler` 对象上调用 `Reference` 方法时引发的异常。

## <a name="syntax"></a>语法

```cpp
class improper_scheduler_reference : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[improper_scheduler_reference](#ctor)|已重载。 构造 `improper_scheduler_reference` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`improper_scheduler_reference`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="improper_scheduler_reference"></a><a name="ctor"></a> improper_scheduler_reference

构造 `improper_scheduler_reference` 对象。

```cpp
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[计划程序类](scheduler-class.md)
