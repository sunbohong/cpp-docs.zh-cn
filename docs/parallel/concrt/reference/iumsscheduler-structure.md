---
description: 了解详细信息： IUMSScheduler 结构
title: IUMSScheduler 结构
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: e42a2e3d39e568ba12cd681053406ce88c7b5dba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334344"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler 结构

工作计划程序的抽象的接口，该工作计划程序希望并发运行时的资源管理器向其传递用户模式计划 (UMS) 线程。 资源管理器使用此接口与 UMS 线程计划程序进行通信。 `IUMSScheduler` 接口继承自 `IScheduler` 接口。

## <a name="syntax"></a>语法

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IUMSScheduler：： SetCompletionList](#setcompletionlist)|`IUMSCompletionList`向 UMS 线程计划程序分配接口。|

## <a name="remarks"></a>备注

如果要实现与资源管理器进行通信的自定义计划程序，并且希望将 UMS 线程传递到计划程序而不是普通 Win32 线程，则应提供接口的实现 `IUMSScheduler` 。 此外，还应将计划程序策略密钥的策略值设置 `SchedulerKind` 为 `UmsThreadDefault` 。 如果策略指定 UMS 线程， `IScheduler` 则作为参数传递给 [IResourceManager：： RegisterScheduler](iresourcemanager-structure.md#registerscheduler) 方法的接口必须是 `IUMSScheduler` 接口。

资源管理器只能在具有 UMS 功能的操作系统上手动使用 UMS 线程。 Windows 7 和更高版本支持 UMS 线程的64位操作系统。 如果创建的计划程序策略的 `SchedulerKind` 键设置为值 `UmsThreadDefault` ，而基础平台不支持 UMS，则 `SchedulerKind` 该策略上的键的值将更改为值 `ThreadScheduler` 。 应始终在预期接收 UMS 线程之前读回此策略值。

`IUMSScheduler`接口是计划程序与资源管理器之间的双向通信通道的一端。 另一端由 `IResourceManager` 和 `ISchedulerProxy` 接口表示，这些接口由资源管理器实现。

## <a name="inheritance-hierarchy"></a>继承层次结构

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>要求

**标头：** concrtrm。h

**命名空间：** 并发

## <a name="iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a> IUMSScheduler：： SetCompletionList 方法

`IUMSCompletionList`向 UMS 线程计划程序分配接口。

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>parameters

*pCompletionList*<br/>
计划程序的完成列表接口。 每个计划程序都有一个列表。

### <a name="remarks"></a>备注

在计划程序请求初始资源分配后，资源管理器将在指定它需要 UMS 线程的计划程序上调用此方法。 计划程序可以使用 `IUMSCompletionList` 接口来确定 UMS 线程代理何时解除阻止。 只有从分配给 UMS 计划程序的虚拟处理器根上运行的线程代理访问此接口才有效。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[IScheduler 结构](ischeduler-structure.md)<br/>
[IUMSCompletionList 结构](iumscompletionlist-structure.md)<br/>
[IResourceManager 结构](iresourcemanager-structure.md)
