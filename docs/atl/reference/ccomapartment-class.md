---
description: 了解详细信息： CComApartment 类
title: CComApartment 类
ms.date: 11/04/2016
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: de51d1eb04bfa0f0760ad741e19b237a9e72dc8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152316"
---
# <a name="ccomapartment-class"></a>CComApartment 类

此类提供对在线程池 EXE 模块中管理单元的支持。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CComApartment
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComApartment：：公寓](#apartment)|标记线程的起始地址。|
|[CComApartment::GetLockCount](#getlockcount)|返回线程的当前锁计数。|
|[CComApartment：： Lock](#lock)|递增线程的锁计数。|
|[CComApartment：： Unlock](#unlock)|减小线程的锁计数。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CComApartment：： m_dwThreadID](#m_dwthreadid)|包含线程的标识符。|
|[CComApartment：： m_hThread](#m_hthread)|包含线程的句柄。|
|[CComApartment：： m_nLockCnt](#m_nlockcnt)|包含线程的当前锁计数。|

## <a name="remarks"></a>备注

`CComApartment`[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)使用来管理线程池 EXE 模块中的单元。 `CComApartment` 提供用于在线程上递增和递减锁计数的方法。

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="ccomapartmentapartment"></a><a name="apartment"></a> CComApartment：：公寓

标记线程的起始地址。

```
DWORD Apartment();
```

### <a name="return-value"></a>返回值

始终为 0。

### <a name="remarks"></a>备注

在 [CComAutoThreadModule：： Init](../../atl/reference/ccomautothreadmodule-class.md#init)期间自动设置。

## <a name="ccomapartmentccomapartment"></a><a name="ccomapartment"></a> CComApartment::CComApartment

构造函数。

```
CComApartment();
```

### <a name="remarks"></a>备注

初始化 `CComApartment` [m_nLockCnt](#m_nlockcnt) 和 [m_hThread](#m_hthread)的数据成员。

## <a name="ccomapartmentgetlockcount"></a><a name="getlockcount"></a> CComApartment::GetLockCount

返回线程的当前锁计数。

```
LONG GetLockCount();
```

### <a name="return-value"></a>返回值

线程的锁计数。

## <a name="ccomapartmentlock"></a><a name="lock"></a> CComApartment：： Lock

递增线程的锁计数。

```
LONG Lock();
```

### <a name="return-value"></a>返回值

可能对诊断或测试有用的值。

### <a name="remarks"></a>备注

由 [CComAutoThreadModule：： Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)调用。

线程上的锁计数用于统计目的。

## <a name="ccomapartmentm_dwthreadid"></a><a name="m_dwthreadid"></a> CComApartment：： m_dwThreadID

包含线程的标识符。

```
DWORD m_dwThreadID;
```

## <a name="ccomapartmentm_hthread"></a><a name="m_hthread"></a> CComApartment：： m_hThread

包含线程的句柄。

```
HANDLE m_hThread;
```

## <a name="ccomapartmentm_nlockcnt"></a><a name="m_nlockcnt"></a> CComApartment：： m_nLockCnt

包含线程的当前锁计数。

```
LONG m_nLockCnt;
```

## <a name="ccomapartmentunlock"></a><a name="unlock"></a> CComApartment：： Unlock

减小线程的锁计数。

```
LONG Unlock();
```

### <a name="return-value"></a>返回值

可能对诊断或测试有用的值。

### <a name="remarks"></a>备注

由 [CComAutoThreadModule：： Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock)调用。

线程上的锁计数用于统计目的。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
