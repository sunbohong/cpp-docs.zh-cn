---
description: 了解详细信息： CAtlAutoThreadModule 类
title: CAtlAutoThreadModule 类
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: d1742488cca84dccfa53753bec40f9081d77f67d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165051"
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule 类

此类实现线程池的单元模型 COM 服务器。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```cpp
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>备注

`CAtlAutoThreadModule` 派生自 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) 并实现一个线程池的单元模型 COM 服务器。 `CAtlAutoThreadModule` 使用 [CComApartment](../../atl/reference/ccomapartment-class.md) 为模块中的每个线程管理单元。

你必须在对象的类定义中使用 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 宏来指定 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 作为类工厂。 然后，应添加派生自的类的单个实例 `CAtlAutoThreadModuleT` ，如 `CAtlAutoThreadModule` 。 例如：

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> 此类替换已过时的 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) 类。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="see-also"></a>请参阅

[CAtlAutoThreadModuleT 类](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[IAtlAutoThreadModule 类](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[Module 类](../../atl/atl-module-classes.md)
