---
description: 了解详细信息： CNonStatelessWorker 类
title: CNonStatelessWorker 类
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: 68457c9594bfaf4d8dd53acd80d7997355c3a3f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141422"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker 类

接收来自线程池的请求，并将其传递到在每个请求上创建并销毁的辅助角色对象。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>parameters

*辅助角色*<br/>
与适用于处理在[CThreadPool](../../atl/reference/cthreadpool-class.md)上排队的请求的[辅助原型](../../atl/reference/worker-archetype.md)一致的工作线程类。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CNonStatelessWorker：： RequestType](#requesttype)|实现 [WorkerArchetype：： RequestType](worker-archetype.md#requesttype)。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CNonStatelessWorker：： Execute](#execute)|实现 [WorkerArchetype：： Execute](worker-archetype.md#execute)。|
|[CNonStatelessWorker：： Initialize](#initialize)|[WorkerArchetype：： Initialize](worker-archetype.md#initialize)的实现。|
|[CNonStatelessWorker：： Terminate](#terminate)|[WorkerArchetype：： Terminate](worker-archetype.md#terminate)的实现。|

## <a name="remarks"></a>备注

此类是用于 [CThreadPool](../../atl/reference/cthreadpool-class.md)的简单工作线程。 此类不提供自身的任何请求处理功能。 相反，它将实例化每个请求的一个 *辅助* 实例，并将其方法的实现委托给该实例。

此类的优点是，它提供了一种简便的方法来更改现有工作线程类的状态模型。 `CThreadPool` 在线程的生存期内将创建单个辅助角色，因此，如果辅助角色类持有状态，它将在多个请求中包含它。 通过在将此类 `CNonStatelessWorker` 与一起使用之前将其包装在模板中 `CThreadPool` ，工作线程的生存期及其持有的状态限制为单个请求。

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a> CNonStatelessWorker：： Execute

实现 [WorkerArchetype：： Execute](worker-archetype.md#execute)。

```cpp
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>备注

此方法在堆栈上创建 *Worker* 类的一个实例，并对该对象调用 [Initialize](worker-archetype.md#initialize) 。 如果初始化成功，则此方法还对同一对象调用 [Execute](worker-archetype.md#execute) 和 [Terminate](worker-archetype.md#terminate) 。

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a> CNonStatelessWorker：： Initialize

[WorkerArchetype：： Initialize](worker-archetype.md#initialize)的实现。

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>返回值

始终返回 TRUE。

### <a name="remarks"></a>备注

此类不会在中执行任何初始化 `Initialize` 。

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a> CNonStatelessWorker：： RequestType

实现 [WorkerArchetype：： RequestType](worker-archetype.md#requesttype)。

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>备注

此类处理与用于 *辅助* 模板参数的类相同的工作项类型。 有关详细信息，请参阅 [CNonStatelessWorker 概述](../../atl/reference/cnonstatelessworker-class.md) 。

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a> CNonStatelessWorker：： Terminate

[WorkerArchetype：： Terminate](worker-archetype.md#terminate)的实现。

```cpp
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>备注

此类不会在中执行任何清理 `Terminate` 。

## <a name="see-also"></a>请参阅

[CThreadPool 类](../../atl/reference/cthreadpool-class.md)<br/>
[工作原型](../../atl/reference/worker-archetype.md)<br/>
[类](../../atl/reference/atl-classes.md)
