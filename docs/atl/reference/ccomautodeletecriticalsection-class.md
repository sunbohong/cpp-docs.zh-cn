---
description: 了解详细信息： CComAutoDeleteCriticalSection 类
title: CComAutoDeleteCriticalSection 类
ms.date: 11/04/2016
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
ms.openlocfilehash: 3c65108917b28b9e4e17210afc54eab6814302b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152329"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection 类

此类提供用于获取和释放关键节对象的所有权的方法。

## <a name="syntax"></a>语法

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>备注

`CComAutoDeleteCriticalSection` 派生自类 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)。 但 `CComAutoDeleteCriticalSection` 会重写 [字词](ccomsafedeletecriticalsection-class.md#term) 方法以 **`private`** 访问，这会强制仅在此类的实例超出范围或从内存中显式删除时才执行内部内存清理。

此类不会对其基类引入其他方法。 有关关键部分帮助器类的详细信息，请参阅 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 和 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>要求

**标头：** atlcore

## <a name="see-also"></a>请参阅

[CComSafeDeleteCriticalSection 类](../../atl/reference/ccomsafedeletecriticalsection-class.md)<br/>
[CComCriticalSection 类](../../atl/reference/ccomcriticalsection-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
