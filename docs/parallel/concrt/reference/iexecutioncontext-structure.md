---
description: 了解详细信息： IExecutionContext 结构
title: IExecutionContext 结构
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 90802229e878546383f683bc99ffedc9cb5411af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122182"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 结构

可以在给定虚拟处理器上运行并可以协作切换上下文的执行上下文的接口。

## <a name="syntax"></a>语法

```cpp
struct IExecutionContext;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IExecutionContext：:D ispatch](#dispatch)|线程代理开始执行特定执行上下文时调用的方法。 这应该是计划程序的主辅助进程。|
|[IExecutionContext：： GetId](#getid)|返回执行上下文的唯一标识符。|
|[IExecutionContext：： GetProxy](#getproxy)|返回正在执行此上下文的线程代理的接口。|
|[IExecutionContext：： GetScheduler](#getscheduler)|返回此执行上下文所属计划程序的接口。|
|[IExecutionContext：： SetProxy](#setproxy)|将线程代理与此执行上下文相关联。 关联的线程代理会在开始执行上下文的方法之前调用此方法 `Dispatch` 。|

## <a name="remarks"></a>备注

如果要实现与并发运行时的资源管理器进行交互的自定义计划程序，则需要实现 `IExecutionContext` 接口。 由资源管理器创建的线程通过执行方法来代表您的计划程序执行工作 `IExecutionContext::Dispatch` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IExecutionContext`

## <a name="requirements"></a>要求

**标头：** concrtrm。h

**命名空间：** 并发

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a> IExecutionContext：:D ispatch 方法

线程代理开始执行特定执行上下文时调用的方法。 这应该是计划程序的主辅助进程。

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>parameters

*pDispatchState*<br/>
指向正在调度此执行上下文的状态的指针。 有关调度状态的详细信息，请参阅 [DispatchState](dispatchstate-structure.md)。

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a> IExecutionContext：： GetId 方法

返回执行上下文的唯一标识符。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>返回值

唯一整数标识符。

### <a name="remarks"></a>备注

你应使用方法 `GetExecutionContextId` 来获取实现接口的对象的唯一标识符 `IExecutionContext` ，然后将接口用作资源管理器提供的方法的参数。 调用函数时，应返回相同的标识符 `GetId` 。

从不同的源获取的标识符可能会导致未定义的行为。

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a> IExecutionContext：： GetProxy 方法

返回正在执行此上下文的线程代理的接口。

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>返回值

一个 `IThreadProxy` 接口。 如果执行上下文的线程代理尚未使用调用进行初始化 `SetProxy` ，则该函数必须返回 `NULL` 。

### <a name="remarks"></a>备注

在 `SetProxy` `IThreadProxy` `Dispatch` 上下文上的中输入方法之前，资源管理器将在执行上下文上调用方法，并将接口用作参数。 应存储此参数，并在调用时将其返回 `GetProxy()` 。

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a> IExecutionContext：： GetScheduler 方法

返回此执行上下文所属计划程序的接口。

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>返回值

一个 `IScheduler` 接口。

### <a name="remarks"></a>备注

需要使用有效的接口初始化执行上下文， `IScheduler` 然后将其用作资源管理器提供的方法的参数。

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a> IExecutionContext：： SetProxy 方法

将线程代理与此执行上下文相关联。 关联的线程代理会在开始执行上下文的方法之前调用此方法 `Dispatch` 。

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>parameters

*pThreadProxy*<br/>
线程代理的一个接口，该接口将 `Dispatch` 在此执行上下文中输入方法。

### <a name="remarks"></a>备注

应保存参数 `pThreadProxy` ，并在对方法的调用上返回 `GetProxy` 。 资源管理器保证当线程代理执行方法时，与执行上下文关联的线程代理将不会更改 `Dispatch` 。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[IScheduler 结构](ischeduler-structure.md)<br/>
[IThreadProxy 结构](ithreadproxy-structure.md)
