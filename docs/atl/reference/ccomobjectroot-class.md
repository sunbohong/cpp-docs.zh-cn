---
description: 了解详细信息： CComObjectRoot 类
title: CComObjectRoot 类
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 924b85ee7ed6e17eb44e753ad16f57251bb189ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142462"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot 类

此 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 的 typedef 在服务器的默认线程模型上是模板化的。

## <a name="syntax"></a>语法

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>备注

`CComObjectRoot` 是 **`typedef`** 服务器默认线程模型上的 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 模板化的。 因此， [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 将引用 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 或 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)。

`CComObjectRootEx` 处理非聚合对象和聚合对象的对象引用计数管理。 如果未对对象进行聚合，则它保存对象引用计数，如果对象正在聚合，则保存指向外部未知的指针。 对于聚合对象， `CComObjectRootEx` 可以使用方法来处理内部对象的失败，并在释放内部接口或删除内部对象时防止删除外部对象。

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="see-also"></a>请参阅

[CComObjectRootEx 类](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject 类](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 类](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject 类](../../atl/reference/ccompolyobject-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
