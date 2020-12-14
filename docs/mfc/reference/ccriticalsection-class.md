---
description: 了解详细信息： CCriticalSection 类
title: CCriticalSection 类
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: 0041eea4453ec02159b26805bd5e7a264a410504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227788"
---
# <a name="ccriticalsection-class"></a>CCriticalSection 类

表示一个 "临界区"，即一次允许一个线程访问资源或代码段的同步对象。

## <a name="syntax"></a>语法

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CCriticalSection::CCriticalSection](#ccriticalsection)|构造 `CCriticalSection` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CCriticalSection：： Lock](#lock)|用于获取对象的访问权限 `CCriticalSection` 。|
|[CCriticalSection：： Unlock](#unlock)|释放 `CCriticalSection` 对象。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CCriticalSection：： operator CRITICAL_SECTION *](#operator_critical_section_star)|检索指向内部 CRITICAL_SECTION 对象的指针。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CCriticalSection：： m_sect](#m_sect)|一个 CRITICAL_SECTION 对象。|

## <a name="remarks"></a>备注

如果一次只能有一个线程可以修改数据或某些其他受控资源，则临界区非常有用。 例如，将节点添加到链接列表是一次只允许一个线程的进程。 通过使用 `CCriticalSection` 对象控制链接列表，一次只能有一个线程可以访问该列表。

> [!NOTE]
> 类的功能 `CCriticalSection` 由实际的 Win32 CRITICAL_SECTION 对象提供。

使用关键部分，而不是 mutex (查看 [CMutex](../../mfc/reference/cmutex-class.md)) 的速度非常重要，并且不会跨进程边界使用该资源。

使用对象的方法有两种 `CCriticalSection` ：独立和嵌入到类中。

- 独立方法：若要使用独立 `CCriticalSection` 对象，请 `CCriticalSection` 在需要时构造对象。 成功从构造函数返回后，通过调用 [lock](#lock)来显式锁定对象。 完成访问关键部分后，调用 [解锁](#unlock) 。 此方法在读取源代码的人员更清晰的情况下更容易出错，因为你必须记得在访问之前和之后锁定并解锁临界区。

   更可取的方法是使用 [CSingleLock](../../mfc/reference/csinglelock-class.md) 类。 它还具有 `Lock` 和 `Unlock` 方法，但如果发生异常，则无需担心解锁资源。

- 嵌入方法还可以通过将 `CCriticalSection` -type 数据成员添加到类并在需要时锁定数据成员，来共享包含多个线程的类。

有关使用对象的详细信息 `CCriticalSection` ，请参阅文章 [多线程处理：如何使用同步类](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>要求

**标头：** afxmt

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a> CCriticalSection::CCriticalSection

构造 `CCriticalSection` 对象。

```
CCriticalSection();
```

### <a name="remarks"></a>备注

若要访问或释放 `CCriticalSection` 对象，请创建一个 [CSingleLock](../../mfc/reference/csinglelock-class.md) 对象，并调用其 [锁定](../../mfc/reference/csinglelock-class.md#lock) 和 [取消锁定](../../mfc/reference/csinglelock-class.md#unlock) 成员函数。 如果该 `CCriticalSection` 对象是独立使用的，则调用它的 [Unlock](#unlock) 成员函数将其释放。

如果构造函数无法分配所需的系统内存，则会自动引发 (类型为 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 的内存异常。

### <a name="example"></a>示例

  请参阅 [CCriticalSection：： Lock](#lock)的示例。

## <a name="ccriticalsectionlock"></a><a name="lock"></a> CCriticalSection：： Lock

调用此成员函数以获取对临界区对象的访问权限。

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>parameters

*dwTimeout*<br/>
`Lock` 忽略此参数值。

### <a name="return-value"></a>返回值

如果函数成功，则为非零值;否则为0。

### <a name="remarks"></a>备注

`Lock` 是一个阻止调用，将不会返回，直到临界区对象收到信号， (变为可用) 。

如果需要计时等待，则可以使用 [CMutex](../../mfc/reference/cmutex-class.md) 对象而不是 `CCriticalSection` 对象。

如果 `Lock` 无法分配所需的系统内存，则会自动引发 (类型为 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 的内存异常。

### <a name="example"></a>示例

此示例通过使用共享对象控制对共享资源的访问， (静态对象) ，从而演示了嵌套的关键部分方法 `_strShared` `CCriticalSection` 。 `SomeMethod`函数演示如何以安全的方式更新共享资源。

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a> CCriticalSection：： m_sect

包含由所有方法使用的临界区对象 `CCriticalSection` 。

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a> CCriticalSection：： operator CRITICAL_SECTION *

检索 CRITICAL_SECTION 的对象。

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>备注

调用此函数可检索指向内部 CRITICAL_SECTION 对象的指针。

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a> CCriticalSection：： Unlock

释放 `CCriticalSection` 对象以供另一个线程使用。

```
BOOL Unlock();
```

### <a name="return-value"></a>返回值

如果该 `CCriticalSection` 对象由线程所有并且发布成功，则为非零; 否则为0。

### <a name="remarks"></a>备注

如果 `CCriticalSection` 使用的是独立的，则 `Unlock` 必须在完成使用关键部分控制的资源之后立即调用。 如果正在使用 [CSingleLock](../../mfc/reference/csinglelock-class.md) 对象，则该对象的 `CCriticalSection::Unlock` `Unlock` 成员函数将调用。

### <a name="example"></a>示例

  请参阅 [CCriticalSection：： Lock](#lock)的示例。

## <a name="see-also"></a>请参阅

[CSyncObject 类](../../mfc/reference/csyncobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CMutex 类](../../mfc/reference/cmutex-class.md)
