---
description: 了解详细信息： CAtlAutoThreadModuleT 类
title: CAtlAutoThreadModuleT 类
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: ad55c78488567c12477c427b99a527b8154ddd22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158408"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT 类

此类提供用于实现线程池单元模型 COM 服务器的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```cpp
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

### <a name="parameters"></a>parameters

*T*<br/>
将实现 COM 服务器的类。

*ThreadAllocator*<br/>
管理线程选择的类。 默认值为 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)。

*dwWait*<br/>
指定超时间隔（以毫秒为单位）。 默认值为 "无限"，这意味着方法的超时间隔永远不会过期。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|此静态函数根据处理器的数量，动态计算并返回 EXE 模块的最大线程数。|

## <a name="remarks"></a>备注

类 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 派生自 `CAtlAutoThreadModuleT` ，以便实现线程池的单元模型 COM 服务器。 它取代了已过时的类 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)。

> [!NOTE]
> 此类不应在 DLL 中使用，因为在卸载 DLL 时，的默认 *dwWait* 值将导致死锁。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a> CAtlAutoThreadModuleT::GetDefaultThreads

此静态函数根据处理器的数量，动态计算并返回 EXE 模块的最大线程数。

```cpp
static int GetDefaultThreads();
```

### <a name="return-value"></a>返回值

要在 EXE 模块中创建的线程数。

### <a name="remarks"></a>备注

如果要使用不同的方法计算线程数，请重写此方法。 默认情况下，线程数取决于处理器数。

## <a name="see-also"></a>请参阅

[IAtlAutoThreadModule 类](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[IAtlAutoThreadModule 类](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Module 类](../../atl/atl-module-classes.md)
