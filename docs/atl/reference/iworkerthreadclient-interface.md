---
description: 了解详细信息： IWorkerThreadClient 接口
title: IWorkerThreadClient 接口
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: fb9113c9380453dad9f647fa2f5a2095ff12cea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157979"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient 接口

`IWorkerThreadClient` 是由 [CWorkerThread](../../atl/reference/cworkerthread-class.md) 类的客户端实现的接口。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
__interface IWorkerThreadClient
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|描述|
|-|-|
|[CloseHandle](#closehandle)|实现此方法可关闭与此对象关联的句柄。|
|[执行](#execute)|实现此方法以在与此对象关联的句柄变为已终止时执行代码。|

## <a name="remarks"></a>备注

当你的代码需要在工作线程上执行，以响应句柄变为信号时，实现此接口。

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a> IWorkerThreadClient：： CloseHandle

实现此方法可关闭与此对象关联的句柄。

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>parameters

*hHandle*<br/>
要关闭的句柄。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

传递给此方法的句柄以前通过调用 [CWorkerThread：： AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)与此对象相关联。

### <a name="example"></a>示例

下面的代码演示的简单实现 `IWorkerThreadClient::CloseHandle` 。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a> IWorkerThreadClient：： Execute

实现此方法以在与此对象关联的句柄变为已终止时执行代码。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>parameters

*dwParam*<br/>
User 参数。

*hObject*<br/>
已发出信号的句柄。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

传递给此方法的句柄和 DWORD/指针以前通过调用 [CWorkerThread：： AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)与此对象相关联。

### <a name="example"></a>示例

下面的代码演示的简单实现 `IWorkerThreadClient::Execute` 。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>请参阅

[类](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread 类](../../atl/reference/cworkerthread-class.md)
