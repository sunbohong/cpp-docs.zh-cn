---
title: IThreadPoolConfig 接口
ms.date: 11/04/2016
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
ms.openlocfilehash: cba82055c292fc966dc2328773cce4aa64d45a64
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835423"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig 接口

此接口提供用于配置线程池的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|说明|
|-|-|
|[GetSize](#getsize)|调用此方法可获取池中的线程数。|
|[GetTimeout](#gettimeout)|调用此方法以获取线程池等待线程关闭的最长时间（以毫秒为单位）。|
|[SetSize](#setsize)|调用此方法可设置池中的线程数。|
|[SetTimeout](#settimeout)|调用此方法以设置线程池等待线程关闭的最长时间（以毫秒为单位）。|

## <a name="remarks"></a>注解

此接口由 [CThreadPool](../../atl/reference/cthreadpool-class.md)实现。

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a> IThreadPoolConfig：： GetSize

调用此方法可获取池中的线程数。

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>参数

*pnNumThreads*<br/>
弄成功接收池中的线程数的变量的地址。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a> IThreadPoolConfig::GetTimeout

调用此方法以获取线程池等待线程关闭的最长时间（以毫秒为单位）。

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>参数

*pdwMaxWait*<br/>
弄成功时的变量地址，接收线程池等待线程关闭的最长时间（以毫秒为单位）。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="example"></a>示例

请参阅 [IThreadPoolConfig：： GetSize](#getsize)。

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a> IThreadPoolConfig：： SetSize

调用此方法可设置池中的线程数。

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>参数

*nNumThreads*<br/>
池中请求的线程数。

如果 *nNumThreads* 为负，则其绝对值将乘以计算机中的处理器数，以获取线程的总数。

如果 *nNumThreads* 为零，ATLS_DEFAULT_THREADSPERPROC 将乘以计算机中的处理器数，以获取线程的总数。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="example"></a>示例

请参阅 [IThreadPoolConfig：： GetSize](#getsize)。

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a> IThreadPoolConfig：： SetTimeout

调用此方法以设置线程池等待线程关闭的最长时间（以毫秒为单位）。

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>参数

*dwMaxWait*<br/>
线程池等待线程关闭所需的最长时间（以毫秒为单位）。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="example"></a>示例

请参阅 [IThreadPoolConfig：： GetSize](#getsize)。

## <a name="see-also"></a>另请参阅

[类](../../atl/reference/atl-classes.md)<br/>
[CThreadPool 类](../../atl/reference/cthreadpool-class.md)
