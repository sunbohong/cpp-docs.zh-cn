---
description: 了解详细信息： CComSimpleThreadAllocator 类
title: CComSimpleThreadAllocator 类
ms.date: 11/04/2016
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
ms.openlocfilehash: 5925707ecd459475d9e9002af76fb76dd9cf9d38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142182"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator 类

此类管理类的线程选择 `CComAutoThreadModule` 。

## <a name="syntax"></a>语法

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComSimpleThreadAllocator：： GetThread](#getthread)|选择一个线程。|

## <a name="remarks"></a>备注

`CComSimpleThreadAllocator` 管理 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)的线程选择。 `CComSimpleThreadAllocator::GetThread` 只需循环遍历每个线程并返回序列中的下一个线程。

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a> CComSimpleThreadAllocator：： GetThread

通过指定序列中的下一个线程来选择一个线程。

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>parameters

*pApt*<br/>
不用于 ATL 的默认实现。

*nThreads*<br/>
EXE 模块中的最大线程数。

### <a name="return-value"></a>返回值

介于零和 (*nThreads* -1) 之间的整数。 标识 EXE 模块中的一个线程。

### <a name="remarks"></a>备注

可以重写 `GetThread` 以提供不同的选择方法或使用 *pApt* 参数。

`GetThread` 由 [CComAutoThreadModule：： CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)调用。

## <a name="see-also"></a>请参阅

[CComApartment 类](../../atl/reference/ccomapartment-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
