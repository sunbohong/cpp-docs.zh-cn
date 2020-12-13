---
description: 了解详细信息： improper_scheduler_detach 类
title: improper_scheduler_detach 类
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
ms.openlocfilehash: 62def23a4a3459c4cb8268b3b0f4df4a77025668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334611"
---
# <a name="improper_scheduler_detach-class"></a>improper_scheduler_detach 类

此类描述在尚未附加到任何使用 `Scheduler` 对象的 `Attach` 方法的计划程序的上下文中调用 `CurrentScheduler::Detach` 方法时引发的异常。

## <a name="syntax"></a>语法

```cpp
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|已重载。 构造 `improper_scheduler_detach` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="improper_scheduler_detach"></a><a name="ctor"></a> improper_scheduler_detach

构造 `improper_scheduler_detach` 对象。

```cpp
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[计划程序类](scheduler-class.md)
