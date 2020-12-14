---
description: 了解详细信息： missing_wait 类
title: missing_wait 类
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: bfbfdf4c2a52573d08c048bac278386aed1dc5a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202179"
---
# <a name="missing_wait-class"></a>missing_wait 类

此类描述执行对象的析构函数时仍有计划到 `task_group` 或 `structured_task_group` 对象的任务时引发的异常。 如果因为堆栈展开为异常的结果而到达析构函数的调用条件，则永远不会引发此异常。

## <a name="syntax"></a>语法

```cpp
class missing_wait : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[missing_wait](#ctor)|已重载。 构造 `missing_wait` 对象。|

## <a name="remarks"></a>备注

缺少异常流，你负责在 `wait` `run_and_wait` `task_group` `structured_task_group` 允许该对象销毁之前，调用或对象的或方法。 运行时引发此异常，表示你忘记调用 `wait` 或 `run_and_wait` 方法。

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`missing_wait`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="missing_wait"></a><a name="ctor"></a> missing_wait

构造 `missing_wait` 对象。

```cpp
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[task_group 类](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group 类](structured-task-group-class.md)
