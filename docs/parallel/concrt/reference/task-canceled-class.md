---
description: 了解详细信息： task_canceled 类
title: task_canceled 类
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: 223a1168464e312c272f770247b3574311ff97ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188399"
---
# <a name="task_canceled-class"></a>task_canceled 类

此类描述了 PPL 任务层为了强制取消当前任务而引发的异常。 `get()`对于已取消的任务，它还由[任务](/visualstudio/extensibility/debugger/task-class-internal-members)的方法引发。

## <a name="syntax"></a>语法

```cpp
class task_canceled : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[task_canceled](#ctor)|已重载。 构造 `task_canceled` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`task_canceled`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="task_canceled"></a><a name="ctor"></a> task_canceled

构造 `task_canceled` 对象。

```cpp
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
