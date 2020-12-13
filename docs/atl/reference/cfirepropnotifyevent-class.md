---
description: 了解详细信息： CFirePropNotifyEvent 类
title: CFirePropNotifyEvent 类
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 09102e67408195751e083807f444c1b028fd2762
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141721"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent 类

此类提供用于通知容器接收器有关控件属性更改的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CFirePropNotifyEvent
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)| (静态) 通知容器接收器控件属性已更改。|
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)| (静态) 通知容器接收器控件属性即将更改。|

## <a name="remarks"></a>备注

`CFirePropNotifyEvent` 具有两个方法，通知容器接收器控件属性已更改或即将更改。

如果实现控件的类派生自，则在 `IPropertyNotifySink` `CFirePropNotifyEvent` 调用或时将调用方法 `FireOnRequestEdit` `FireOnChanged` 。 如果控件类不是从派生的 `IPropertyNotifySink` ，则对这些函数的调用将返回 S_OK。

有关创建控件的详细信息，请参阅 [ATL 教程](../../atl/active-template-library-atl-tutorial.md)。

## <a name="requirements"></a>要求

**标头：** atlctl

## <a name="cfirepropnotifyeventfireonchanged"></a><a name="fireonchanged"></a> CFirePropNotifyEvent::FireOnChanged

通知) 指定对象属性已更改的对象的每个连接点 (所有连接的 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 接口。

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>parameters

*pUnk*<br/>
中指向发送通知的对象的的指针 `IUnknown` 。

*dispID*<br/>
中已更改的属性的标识符。

### <a name="return-value"></a>返回值

标准的 HRESULT 值之一。

### <a name="remarks"></a>备注

即使您的控件不支持连接点，也可以安全地调用此函数。

## <a name="cfirepropnotifyeventfireonrequestedit"></a><a name="fireonrequestedit"></a> CFirePropNotifyEvent::FireOnRequestEdit

通知) 指定对象属性将要更改的对象的每个连接点 (所有连接的 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 接口。

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>parameters

*pUnk*<br/>
中指向发送通知的对象的的指针 `IUnknown` 。

*dispID*<br/>
中要更改的属性的标识符。

### <a name="return-value"></a>返回值

标准的 HRESULT 值之一。

### <a name="remarks"></a>备注

即使您的控件不支持连接点，也可以安全地调用此函数。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
