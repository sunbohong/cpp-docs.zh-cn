---
description: 了解详细信息： CNoWorkerThread 类
title: CNoWorkerThread 类
ms.date: 11/04/2016
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
ms.openlocfilehash: 5159c04a8390f8933291f697faccedb7353fb48e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141409"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread 类

如果要禁用动态缓存维护，请使用此类作为用于 `MonitorClass` 缓存类的模板参数的参数。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CNoWorkerThread
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CNoWorkerThread::AddHandle](#addhandle)|非功能性等效于 [CWorkerThread：： AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)。|
|[CNoWorkerThread::AddTimer](#addtimer)|非功能性等效于 [CWorkerThread：： AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)。|
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|非功能性等效于 [CWorkerThread：： GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)。|
|[CNoWorkerThread::GetThreadId](#getthreadid)|非功能性等效于 [CWorkerThread：： GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)。|
|[CNoWorkerThread：： Initialize](#initialize)|非功能性等效于 [CWorkerThread：： Initialize](../../atl/reference/cworkerthread-class.md#initialize)。|
|[CNoWorkerThread::RemoveHandle](#removehandle)|非功能性等效于 [CWorkerThread：： RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)。|
|[CNoWorkerThread：： Shutdown](#shutdown)|非功能性等效于 [CWorkerThread：： Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)。|

## <a name="remarks"></a>备注

此类提供与 [CWorkerThread](../../atl/reference/cworkerthread-class.md)相同的公共接口。 此接口应由 `MonitorClass` 模板参数提供给缓存类。

实现此类中的方法不执行任何操作。 返回 HRESULT 的方法始终返回 S_OK，返回句柄或线程 ID 的方法将始终返回0。

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a> CNoWorkerThread::AddHandle

非功能性等效于 [CWorkerThread：： AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)。

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>返回值

始终返回 S_OK。

### <a name="remarks"></a>备注

此类提供的实现不执行任何操作。

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a> CNoWorkerThread::AddTimer

非功能性等效于 [CWorkerThread：： AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)。

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>返回值

始终返回 S_OK。

### <a name="remarks"></a>备注

此类提供的实现不执行任何操作。

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a> CNoWorkerThread::GetThreadHandle

非功能性等效于 [CWorkerThread：： GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)。

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>返回值

始终返回 NULL。

### <a name="remarks"></a>备注

此类提供的实现不执行任何操作。

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a> CNoWorkerThread::GetThreadId

非功能性等效于 [CWorkerThread：： GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)。

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>返回值

始终返回 0。

### <a name="remarks"></a>备注

此类提供的实现不执行任何操作。

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a> CNoWorkerThread：： Initialize

非功能性等效于 [CWorkerThread：： Initialize](../../atl/reference/cworkerthread-class.md#initialize)。

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>返回值

始终返回 S_OK。

### <a name="remarks"></a>备注

此类提供的实现不执行任何操作。

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a> CNoWorkerThread::RemoveHandle

非功能性等效于 [CWorkerThread：： RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)。

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>返回值

始终返回 S_OK。

### <a name="remarks"></a>备注

此类提供的实现不执行任何操作。

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a> CNoWorkerThread：： Shutdown

非功能性等效于 [CWorkerThread：： Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)。

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>返回值

始终返回 S_OK。

### <a name="remarks"></a>备注

此类提供的实现不执行任何操作。
