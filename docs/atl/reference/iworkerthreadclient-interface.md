---
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
ms.openlocfilehash: aa72f090a006d6936339582a919b0faf5cab6b03
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835345"
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

|名称|说明|
|-|-|
|[CloseHandle](#closehandle)|实现此方法可关闭与此对象关联的句柄。|
|[执行](#execute)|实现此方法以在与此对象关联的句柄变为已终止时执行代码。|

## <a name="remarks"></a>注解

当你的代码需要在工作线程上执行，以响应句柄变为信号时，实现此接口。

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a> IWorkerThreadClient：： CloseHandle

实现此方法可关闭与此对象关联的句柄。

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>参数

*hHandle*<br/>
要关闭的句柄。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>注解

传递给此方法的句柄以前通过调用 [CWorkerThread：： AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)与此对象相关联。

### <a name="example"></a>示例

下面的代码演示的简单实现 `IWorkerThreadClient::CloseHandle` 。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a> IWorkerThreadClient：： Execute

实现此方法以在与此对象关联的句柄变为已终止时执行代码。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>参数

*dwParam*<br/>
User 参数。

*hObject*<br/>
已发出信号的句柄。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>注解

传递给此方法的句柄和 DWORD/指针以前通过调用 [CWorkerThread：： AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)与此对象相关联。

### <a name="example"></a>示例

下面的代码演示的简单实现 `IWorkerThreadClient::Execute` 。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>另请参阅

[类](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread 类](../../atl/reference/cworkerthread-class.md)
