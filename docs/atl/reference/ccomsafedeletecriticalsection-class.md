---
title: CComSafeDeleteCriticalSection 类
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: 115cbd466f51db271f4be65ce708fe54c7f2b2ce
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833629"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection 类

此类提供用于获取和释放关键节对象的所有权的方法。

## <a name="syntax"></a>语法

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|说明|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|构造函数。|
|[CComSafeDeleteCriticalSection：： ~ CComSafeDeleteCriticalSection](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|说明|
|----------|-----------------|
|[CComSafeDeleteCriticalSection：： Init](#init)|创建并初始化一个临界区对象。|
|[CComSafeDeleteCriticalSection：： Lock](#lock)|获取临界区对象的所有权。|
|[CComSafeDeleteCriticalSection：： Term](#term)|释放由临界区对象使用的系统资源。|

### <a name="data-members"></a>数据成员

|数据成员|说明|
|-|-|
|[m_bInitialized](#m_binitialized)|标记内部对象是否 `CRITICAL_SECTION` 已初始化。|

## <a name="remarks"></a>注解

`CComSafeDeleteCriticalSection` 派生自类 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)。 但是， `CComSafeDeleteCriticalSection` 通过 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)提供其他安全机制。

当的实例 `CComSafeDeleteCriticalSection` 超出范围或从内存中显式删除时，将自动清除基础临界区对象（如果它仍有效）。 此外，如果基础临界区对象尚未分配或已从内存中释放，则 [CComSafeDeleteCriticalSection：： Term](#term) 方法将正常退出。

有关关键部分帮助器类的详细信息，请参阅 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>要求

**标头：** atlcore

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a> CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection

构造函数。

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>注解

将 [m_bInitialized](#m_binitialized) 数据成员设置为 FALSE。

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a> CComSafeDeleteCriticalSection：： ~ CComSafeDeleteCriticalSection

析构函数。

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>注解

`CRITICAL_SECTION`如果[m_bInitialized](#m_binitialized)数据成员设置为 TRUE，则从内存中释放内部对象。

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a> CComSafeDeleteCriticalSection：： Init

调用 [Init](/visualstudio/debugger/init) 的基类实现，如果成功，则将 [M_BINITIALIZED](#m_binitialized) 设置为 TRUE。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>返回值

返回 [CComCriticalSection：： Init](../../atl/reference/ccomcriticalsection-class.md#init)的结果。

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a> CComSafeDeleteCriticalSection：： Lock

调用 [锁](ccomcriticalsection-class.md#lock)的基类实现。

```
HRESULT Lock();
```

### <a name="return-value"></a>返回值

返回 [CComCriticalSection：： Lock](../../atl/reference/ccomcriticalsection-class.md#lock)的结果。

### <a name="remarks"></a>注解

此方法假定在输入时将 [m_bInitialized](#m_binitialized) 数据成员设置为 TRUE。 如果不满足此条件，则会在调试版本中生成断言。

有关函数行为的详细信息，请参阅 [CComCriticalSection：： Lock](../../atl/reference/ccomcriticalsection-class.md#lock)。

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a> CComSafeDeleteCriticalSection：： m_bInitialized

标记内部对象是否 `CRITICAL_SECTION` 已初始化。

```
bool m_bInitialized;
```

### <a name="remarks"></a>注解

`m_bInitialized`数据成员用于跟踪 `CRITICAL_SECTION` 与[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)类关联的基础对象的有效性。 `CRITICAL_SECTION`如果此标志未设置为 TRUE，则将不会尝试从内存中释放基础对象。

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a> CComSafeDeleteCriticalSection：： Term

如果内部对象有效，将调用 [CComCriticalSection：： Term](../../atl/reference/ccomcriticalsection-class.md#term) 的基类实现 `CRITICAL_SECTION` 。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>返回值

返回 [CComCriticalSection：： Term](../../atl/reference/ccomcriticalsection-class.md#term)的结果，如果在输入时将 [M_BINITIALIZED](#m_binitialized) 设置为 FALSE，则返回 S_OK。

### <a name="remarks"></a>注解

即使内部对象无效，也可以安全地调用此方法 `CRITICAL_SECTION` 。 如果 [m_bInitialized](#m_binitialized) 数据成员设置为 TRUE，则此类的析构函数将调用此方法。

## <a name="see-also"></a>另请参阅

[CComCriticalSection 类](../../atl/reference/ccomcriticalsection-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
