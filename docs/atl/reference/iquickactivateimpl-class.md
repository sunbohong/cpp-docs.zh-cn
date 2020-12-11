---
description: 了解详细信息： IQuickActivateImpl 类
title: IQuickActivateImpl 类
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 1e9dc2891351512ec3ebe54ebe6711ee9d4a3fa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158122"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl 类

此类将容器的控件初始化组合为单个调用。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IQuickActivateImpl` 。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|检索正在运行的控件的当前显示大小。|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|快速初始化正在加载的控件。|
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|通知控制容器分配给它的显示空间量。|

## <a name="remarks"></a>备注

在单个调用中组合初始化时， [IQuickActivate](/windows/win32/api/ocidl/nn-ocidl-iquickactivate) 接口可帮助容器避免延迟加载控件。 `QuickActivate`方法允许容器传递指向[QACONTAINER](/windows/win32/api/ocidl/ns-ocidl-qacontainer)结构的指针，该结构保存指向控件所需的所有接口的指针。 返回时，控件向后传递一个指向 [QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol) 结构的指针，该结构包含指向其自己的接口的指针，这些接口由容器使用。 类 `IQuickActivateImpl` 提供的默认实现 `IQuickActivate` ，并 `IUnknown` 通过在调试版本中将信息发送到转储设备来实现。

**相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)， [创建 atl 项目](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>要求

**标头：** atlctl

## <a name="iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a> IQuickActivateImpl::GetContentExtent

检索正在运行的控件的当前显示大小。

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>备注

该大小用于控件的完全呈现，并且是在 HIMETRIC 单元中指定的。

请参阅 Windows SDK 中的 [IQuickActivate：： GetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) 。

## <a name="iquickactivateimplquickactivate"></a><a name="quickactivate"></a> IQuickActivateImpl::QuickActivate

快速初始化正在加载的控件。

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>备注

结构包含指向控件所需的接口的指针以及某些环境属性的值。 返回后，控件将传递一个指向 [QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol) 结构的指针，该结构包含指向其自己的容器所需接口的指针以及其他状态信息。

请参阅 Windows SDK 中的 [IQuickActivate：： QuickActivate](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate) 。

## <a name="iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a> IQuickActivateImpl::SetContentExtent

通知控制容器分配给它的显示空间量。

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>备注

大小是在 HIMETRIC 单位中指定的。

请参阅 Windows SDK 中的 [IQuickActivate：： SetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) 。

## <a name="see-also"></a>请参阅

[CComControl 类](../../atl/reference/ccomcontrol-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
