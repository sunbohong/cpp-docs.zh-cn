---
description: 了解详细信息： improper_scheduler_attach 类
title: improper_scheduler_attach 类
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach::improper_scheduler_attach
helpviewer_keywords:
- improper_scheduler_attach class
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
ms.openlocfilehash: 755cd72d20eb88dbd1ff7c58586f0aaf3b964a6a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334623"
---
# <a name="improper_scheduler_attach-class"></a>improper_scheduler_attach 类

此类描述在已附加到当前上下文的 `Scheduler` 对象上调用 `Attach` 方法时引发的异常。

## <a name="syntax"></a>语法

```cpp
class improper_scheduler_attach : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[improper_scheduler_attach](#ctor)|已重载。 构造 `improper_scheduler_attach` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`improper_scheduler_attach`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="improper_scheduler_attach"></a><a name="ctor"></a> improper_scheduler_attach

构造 `improper_scheduler_attach` 对象。

```cpp
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[计划程序类](scheduler-class.md)
