---
description: 了解详细信息： IPropertyNotifySinkCP 类
title: IPropertyNotifySinkCP 类
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: 096a24a22634be23c7ede955c7ae49c3dd963f66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158356"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP 类

此类公开 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 接口作为可连接对象上的传出接口。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IPropertyNotifySinkCP` 。

*CDV*<br/>
一个类，用于管理连接点与其接收器之间的连接。 默认值为 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)，这允许无限制的连接。 你还可以使用 [CComUnkArray](../../atl/reference/ccomunkarray-class.md)，它指定固定数目的连接。

## <a name="remarks"></a>备注

`IPropertyNotifySinkCP` 通过其基类 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)继承所有方法。

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)接口允许接收器对象接收有关属性更改的通知。 类将 `IPropertyNotifySinkCP` 此接口公开为可连接对象上的传出接口。 客户端必须 `IPropertyNotifySink` 在接收器上实现方法。

`IPropertyNotifySinkCP`若要创建表示接口的连接点，请从派生类 `IPropertyNotifySink` 。

有关在 ATL 中使用连接点的详细信息，请参阅文章 [连接点](../../atl/atl-connection-points.md)。

## <a name="requirements"></a>要求

**标头：** atlctl

## <a name="see-also"></a>请参阅

[IConnectionPointImpl 类](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[IConnectionPointContainerImpl 类](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
