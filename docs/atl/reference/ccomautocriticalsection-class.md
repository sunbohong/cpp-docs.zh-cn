---
description: 了解详细信息： CComAutoCriticalSection 类
title: CComAutoCriticalSection 类
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 2441c714b95a3bbefed4a699055d14c6915cffda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146960"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection 类

`CComAutoCriticalSection` 提供用于获取和释放关键节对象的所有权的方法。

## <a name="syntax"></a>语法

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|构造函数。|
|[CComAutoCriticalSection：： ~ CComAutoCriticalSection](#dtor)|析构函数。|

## <a name="remarks"></a>备注

`CComAutoCriticalSection` 类似于类 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)，但 `CComAutoCriticalSection` 在构造函数中自动初始化临界区对象。

通常，使用 `CComAutoCriticalSection` **`typedef`** 名称 [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection)。 `CComAutoCriticalSection`当使用[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)时，此名称引用。

`Init` `Term` 使用此类时， [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)中的和方法不可用。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>要求

**标头：** atlcore

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a> CComAutoCriticalSection::CComAutoCriticalSection

构造函数。

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>备注

调用 Win32 函数 [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)，该函数初始化临界区对象。

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a> CComAutoCriticalSection：： ~ CComAutoCriticalSection

析构函数。

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>备注

析构函数调用 [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)，后者释放由临界区对象使用的所有系统资源。

## <a name="see-also"></a>请参阅

[CComFakeCriticalSection 类](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection 类](../../atl/reference/ccomcriticalsection-class.md)
