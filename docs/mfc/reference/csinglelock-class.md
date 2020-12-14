---
description: 了解详细信息： CSingleLock 类
title: CSingleLock 类
ms.date: 11/04/2016
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
ms.openlocfilehash: 7fa4fe32ce38bf47ede1b6ac133d1a057907f9c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342851"
---
# <a name="csinglelock-class"></a>CSingleLock 类

表示多线程程序中用于控制对一个资源的访问的访问控制机制。

## <a name="syntax"></a>语法

```
class CSingleLock
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|构造 `CSingleLock` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSingleLock：： IsLocked](#islocked)|确定对象是否已锁定。|
|[CSingleLock：： Lock](#lock)|等待同步对象。|
|[CSingleLock：： Unlock](#unlock)|释放同步对象。|

## <a name="remarks"></a>备注

`CSingleLock` 没有基类。

为了使用同步类 [CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)和 [CEvent](../../mfc/reference/cevent-class.md)，你必须创建一个 `CSingleLock` 或 [CMultiLock](../../mfc/reference/cmultilock-class.md) 对象来等待并释放同步对象。 `CSingleLock`当只需等待一个对象时使用。 `CMultiLock`当有多个对象可以在特定时间使用时，请使用。

若要使用 `CSingleLock` 对象，请在受控资源的类中的成员函数内调用其构造函数。 然后调用 [IsLocked](#islocked) 成员函数来确定资源是否可用。 如果是，则继续执行成员函数的其余部分。 如果资源不可用，请等待指定的时间，释放资源，或返回失败。 完成资源的使用后，如果[](#unlock) `CSingleLock` 要再次使用该对象，请调用 Unlock 函数，或允许 `CSingleLock` 对象被销毁。

`CSingleLock` 对象要求存在从 [CSyncObject](../../mfc/reference/csyncobject-class.md)派生的对象。 这通常是受控资源的类的数据成员。 有关如何使用对象的详细信息 `CSingleLock` ，请参阅文章 [多线程处理：如何使用同步类](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CSingleLock`

## <a name="requirements"></a>要求

**标头：** afxmt

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a> CSingleLock::CSingleLock

构造 `CSingleLock` 对象。

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>parameters

*pObject*<br/>
指向要访问的同步对象。 不能为 NULL。

*bInitialLock*<br/>
指定是否最初尝试访问提供的对象。

### <a name="remarks"></a>备注

通常从受控资源的访问成员函数内调用此函数。

### <a name="example"></a>示例

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a> CSingleLock：： IsLocked

确定与对象关联的对象 `CSingleLock` 是否非终止 (不可用) 。

```
BOOL IsLocked();
```

### <a name="return-value"></a>返回值

如果对象被锁定，则为非零值;否则为0。

### <a name="example"></a>示例

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a> CSingleLock：： Lock

调用此函数可获取对提供给构造函数的同步对象所控制的资源的访问权限 `CSingleLock` 。

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>parameters

*dwTimeOut*<br/>
指定等待同步对象)  (可用的时间量。 如果是无限的， `Lock` 将等待直到对象收到信号后才返回。

### <a name="return-value"></a>返回值

如果函数成功，则为非零值;否则为0。

### <a name="remarks"></a>备注

如果同步对象处于终止状态， `Lock` 则将成功返回，并且该线程现在拥有该对象。 如果同步对象为非终止 (不可用) ， `Lock` 将等待同步对象在 *dwTimeOut* 参数中指定的毫秒数后终止。 如果同步对象在指定的时间内未发出信号，则 `Lock` 返回失败。

### <a name="example"></a>示例

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a> CSingleLock：： Unlock

释放由拥有的同步对象 `CSingleLock` 。

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>parameters

*lCount*<br/>
要发布的访问次数。 必须大于 0。 如果指定的量会导致对象的计数超过其最大值，则不会更改计数，并且函数返回 FALSE。

*lPrevCount*<br/>
指向一个变量，用于接收同步对象的前一个计数。 如果为 NULL，则不返回前一个计数。

### <a name="return-value"></a>返回值

如果函数成功，则为非零值;否则为0。

### <a name="remarks"></a>备注

此函数由 `CSingleLock` 的析构函数调用。

如果需要释放一个信号量的多个访问计数，请使用第二种形式的 `Unlock` ，并指定要释放的访问次数。

### <a name="example"></a>示例

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock 类](../../mfc/reference/cmultilock-class.md)
