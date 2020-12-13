---
description: 了解详细信息： IUMSUnblockNotification 结构
title: IUMSUnblockNotification 结构
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: bec40ee1e7326ad37e205c3035f965cb3f0ec8d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334308"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 结构

表示来自资源管理器的通知，说明阻止并触发返回到计划程序的指定计划上下文的线程代理已解除阻止，并已准备好进行计划。 一旦重新计划该线程代理的关联执行上下文（从 `GetContext` 方法返回），此接口将变得无效。

## <a name="syntax"></a>语法

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IUMSUnblockNotification：： GetContext](#getcontext)|返回 `IExecutionContext` 与已解除阻止的线程代理关联的执行上下文的接口。 此方法返回并且基础执行上下文通过调用方法重新计划后 `IThreadProxy::SwitchTo` ，此接口将不再有效。|
|[IUMSUnblockNotification：： GetNextUnblockNotification](#getnextunblocknotification)|返回 `IUMSUnblockNotification` 从方法返回的链中的下一个接口 `IUMSCompletionList::GetUnblockNotifications` 。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`IUMSUnblockNotification`

## <a name="requirements"></a>要求

**标头：** concrtrm。h

**命名空间：** 并发

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a> IUMSUnblockNotification：： GetContext 方法

返回 `IExecutionContext` 与已解除阻止的线程代理关联的执行上下文的接口。 此方法返回并且基础执行上下文通过调用方法重新计划后 `IThreadProxy::SwitchTo` ，此接口将不再有效。

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>返回值

`IExecutionContext`执行上下文到已取消阻止的线程代理的接口。

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a> IUMSUnblockNotification：： GetNextUnblockNotification 方法

返回 `IUMSUnblockNotification` 从方法返回的链中的下一个接口 `IUMSCompletionList::GetUnblockNotifications` 。

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>返回值

`IUMSUnblockNotification`从方法返回的链中的下一个接口 `IUMSCompletionList::GetUnblockNotifications` 。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[IUMSScheduler 结构](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 结构](iumscompletionlist-structure.md)
