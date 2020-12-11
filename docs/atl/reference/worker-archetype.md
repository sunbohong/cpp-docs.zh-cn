---
description: 了解详细信息：工作线程原型
title: 工作原型
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 8cb8c2b281bbdc074bb700b77a856f4d26c26cf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157563"
---
# <a name="worker-archetype"></a>工作原型

符合 *辅助* 原型的类提供用于处理线程池上排队的工作项的代码。

**实现**

若要实现符合此原型的类，类必须提供以下功能：

|方法|描述|
|------------|-----------------|
|[初始化](#initialize)|调用以初始化辅助对象，然后将请求传递给 [执行](#execute)。|
|[执行](#execute)|调用以处理工作项。|
|Terminate|调用以在所有请求都传递到 [执行](#execute)之后对工作对象进行初始化。|

|Typedef|说明|
|-------------|-----------------|
|[RequestType](#requesttype)|可由 worker 类处理的工作项类型的 typedef。|

典型的 *辅助角色* 类如下所示：

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**现有实现**

这些类符合以下原型：

|类|描述|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|接收来自线程池的请求，并将其传递给为每个请求创建并销毁的辅助角色对象。|

**使用**

这些模板参数需要类符合以下原型：

|参数名称|使用者|
|--------------------|-------------|
|*辅助角色*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*辅助角色*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>要求

**标头：** atlutil

## <a name="workerarchetypeexecute"></a><a name="execute"></a> WorkerArchetype：： Execute

调用以处理工作项。

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>parameters

*请求*<br/>
要处理的工作项。 工作项的类型与相同 `RequestType` 。

*pvWorkerParam*<br/>
辅助类理解的自定义参数。 也传递给 `WorkerArchetype::Initialize` 和 `Terminate` 。

*pOverlapped*<br/>
指向用于创建在其上排队工作项的队列的 [重叠](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) 结构的指针。

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a> WorkerArchetype：： Initialize

调用以在将任何请求传递到之前初始化辅助对象 `WorkerArchetype::Execute` 。

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>parameters

*pvParam*<br/>
辅助类理解的自定义参数。 也传递给 `WorkerArchetype::Terminate` 和 `WorkerArchetype::Execute` 。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a> WorkerArchetype：： RequestType

可由 worker 类处理的工作项类型的 typedef。

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>备注

此类型必须用作的第一个参数 `WorkerArchetype::Execute` ，并且必须能够与 ULONG_PTR 强制转换。

## <a name="workerarchetypeterminate"></a><a name="terminate"></a> WorkerArchetype：： Terminate

调用以在所有请求都传递到) 后对辅助对象进行初始化 `WorkerArchetype::Execute` 。

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>parameters

*pvParam*<br/>
辅助类理解的自定义参数。 也传递给 `WorkerArchetype::Initialize` 和 `WorkerArchetype::Execute` 。

## <a name="see-also"></a>请参阅

[概念](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM 桌面组件](../../atl/atl-com-desktop-components.md)
