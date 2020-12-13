---
description: 了解详细信息： IPointerInactiveImpl 类
title: IPointerInactiveImpl 类
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 0ee5c103582ff68c80edd36316179b47a1b7931d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139303"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl 类

此类实现 `IUnknown` 和 [IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) 接口方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IPointerInactiveImpl` 。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|检索对象的当前激活策略。 ATL 实现返回 E_NOTIMPL。|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|通知对象：鼠标指针已移动到该对象，指示对象可以引发鼠标事件。 ATL 实现返回 E_NOTIMPL。|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|设置非活动对象的鼠标指针。 ATL 实现返回 E_NOTIMPL。|

## <a name="remarks"></a>备注

非活动对象是一个简单的加载或运行的对象。 与活动对象不同，非活动对象不能接收 Windows 鼠标和键盘消息。 因此，非活动对象使用更少的资源，通常更有效。

[IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive)接口允许对象支持最小级别的鼠标交互，同时保持不活动状态。 此功能对控件特别有用。

类 `IPointerInactiveImpl` `IPointerInactive` 通过只返回 E_NOTIMPL 来实现方法。 但是，它 `IUnknown` 通过在调试版本中将信息发送到转储设备来实现。

**相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)， [创建 atl 项目](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>要求

**标头：** atlctl

## <a name="ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a> IPointerInactiveImpl::GetActivationPolicy

检索对象的当前激活策略。

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>返回值

返回 E_NOTIMPL。

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPointerInactive：： GetActivationPolicy](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) 。

## <a name="ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a> IPointerInactiveImpl::OnInactiveMouseMove

通知对象：鼠标指针已移动到该对象，指示对象可以引发鼠标事件。

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>返回值

返回 E_NOTIMPL。

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPointerInactive：： OnInactiveMouseMove](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) 。

## <a name="ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a> IPointerInactiveImpl::OnInactiveSetCursor

设置非活动对象的鼠标指针。

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>返回值

返回 E_NOTIMPL。

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPointerInactive：： OnInactiveSetCursor](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) 。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
