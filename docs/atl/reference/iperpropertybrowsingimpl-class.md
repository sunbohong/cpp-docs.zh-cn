---
description: 了解详细信息： IPerPropertyBrowsingImpl 类
title: IPerPropertyBrowsingImpl 类
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: eba17c0011343f50f586b13086dc76229f08ba3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139342"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl 类

此类实现 `IUnknown` 并允许客户端访问对象的属性页中的信息。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IPerPropertyBrowsingImpl` 。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|检索描述给定属性的字符串。|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|检索一个字符串数组，该数组对应于给定属性可接受的值。|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|检索一个变量，该变量包含由给定 DISPID 标识的属性的值。 DISPID 与从检索的字符串名称关联 `GetPredefinedStrings` 。 ATL 实现返回 E_NOTIMPL。|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|检索与给定属性相关联的属性页的 CLSID。|

## <a name="remarks"></a>备注

[IPerPropertyBrowsing](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing)接口允许客户端访问对象的属性页中的信息。 类 `IPerPropertyBrowsingImpl` 提供此接口的默认实现，并 `IUnknown` 通过在调试版本中将信息发送到转储设备来实现。

> [!NOTE]
> 如果使用 Microsoft Access 作为容器应用程序，则必须从派生类 `IPerPropertyBrowsingImpl` 。 否则，Access 将不会加载您的控件。

**相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)， [创建 atl 项目](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>要求

**标头：** atlctl

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a> IPerPropertyBrowsingImpl::GetDisplayString

检索描述给定属性的字符串。

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPerPropertyBrowsing：： GetDisplayString](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) 。

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a> IPerPropertyBrowsingImpl::GetPredefinedStrings

用零个项填充每个数组。

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>返回值

ATL 的 [GetPredefinedValue](#getpredefinedvalue) 实现将返回 E_NOTIMPL。

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPerPropertyBrowsing：： GetPredefinedStrings](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) 。

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a> IPerPropertyBrowsingImpl::GetPredefinedValue

检索一个变量，该变量包含由给定 DISPID 标识的属性的值。 DISPID 与从检索的字符串名称关联 `GetPredefinedStrings` 。

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>返回值

返回 E_NOTIMPL。

### <a name="remarks"></a>备注

ATL 的 [GetPredefinedStrings](#getpredefinedstrings) 实现不检索相应的字符串。

请参阅 Windows SDK 中的 [IPerPropertyBrowsing：： GetPredefinedValue](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) 。

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a> IPerPropertyBrowsingImpl::MapPropertyToPage

检索与指定属性关联的属性页的 CLSID。

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>备注

ATL 使用对象的属性映射来获取此信息。

请参阅 Windows SDK 中的 [IPerPropertyBrowsing：： MapPropertyToPage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) 。

## <a name="see-also"></a>请参阅

[IPropertyPageImpl 类](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl 类](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
