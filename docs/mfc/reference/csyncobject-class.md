---
description: 了解详细信息： CSyncObject 类
title: CSyncObject 类
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: 5743f632f9a8c482ac15995e8d2429851ba015d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318593"
---
# <a name="csyncobject-class"></a>CSyncObject 类

一个纯虚拟类，提供 Win32 中的同步对象所共有的功能。

## <a name="syntax"></a>语法

```
class CSyncObject : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|构造 `CSyncObject` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSyncObject：： Lock](#lock)|获得对同步对象的访问权限。|
|[CSyncObject：： Unlock](#unlock)|获得对同步对象的访问权限。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CSyncObject：： operator 句柄](#operator_handle)|提供对同步对象的访问。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CSyncObject：： m_hObject](#m_hobject)|基础同步对象的句柄。|

## <a name="remarks"></a>备注

Microsoft 基础类库提供了多个派生自的类 `CSyncObject` 。 这些是 [CEvent](../../mfc/reference/cevent-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)和 [CSemaphore](../../mfc/reference/csemaphore-class.md)。

有关如何使用同步对象的信息，请参阅文章 [多线程处理：如何使用同步类](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>要求

**标头：** afxmt

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a> CSyncObject::CSyncObject

用提供的名称构造同步对象。

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>parameters

*pstrName*<br/>
对象的名称。 如果为 NULL，则 *pstrName* 将为 null。

## <a name="csyncobjectlock"></a><a name="lock"></a> CSyncObject：： Lock

调用此函数可获取对由同步对象控制的资源的访问权限。

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>parameters

*dwTimeout*<br/>
指定等待同步对象)  (可用的时间量（以毫秒为单位）。 如果是无限的， `Lock` 将等待直到对象收到信号后才返回。

### <a name="return-value"></a>返回值

如果函数成功，则为非零值;否则为0。

### <a name="remarks"></a>备注

如果同步对象处于终止状态， `Lock` 则将成功返回，并且该线程现在拥有该对象。 如果同步对象为非终止 (不可用) ， `Lock` 将等待同步对象在 *dwTimeOut* 参数中指定的毫秒数后终止。 如果同步对象在指定的时间内未发出信号，则 `Lock` 返回失败。

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a> CSyncObject：： m_hObject

基础同步对象的句柄。

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a> CSyncObject：： operator 句柄

使用此运算符可获取对象的句柄 `CSyncObject` 。

```
operator HANDLE() const;
```

### <a name="return-value"></a>返回值

如果成功，则为同步对象的句柄;否则为 NULL。

### <a name="remarks"></a>备注

您可以使用句柄直接调用 Windows Api。

## <a name="csyncobjectunlock"></a><a name="unlock"></a> CSyncObject：： Unlock

`Unlock`不带参数的声明是纯虚函数，并且必须由派生自的所有类重写 `CSyncObject` 。

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>parameters

*lCount*<br/>
默认实现不使用。

*lpPrevCount*<br/>
默认实现不使用。

### <a name="return-value"></a>返回值

默认实现始终返回 TRUE。

### <a name="remarks"></a>备注

具有两个参数的声明的默认实现始终返回 TRUE。 调用此函数以释放对调用线程拥有的同步对象的访问权限。 第二个声明为同步对象（如允许多个受控制资源访问的信号量）提供。

## <a name="see-also"></a>请参阅

[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)
