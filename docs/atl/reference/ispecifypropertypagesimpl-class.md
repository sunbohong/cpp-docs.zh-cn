---
description: 了解详细信息： ISpecifyPropertyPagesImpl 类
title: ISpecifyPropertyPagesImpl 类
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 528fafa0473a4aa803e1c1d17a24b2d27584c33a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158044"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl 类

此类实现 `IUnknown` 并提供 [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) 接口的默认实现。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `ISpecifyPropertyPagesImpl` 。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|填充一个 UUID 值的计数数组。 每个 UUID 对应于可显示在对象属性表中的属性页之一的 CLSID。|

## <a name="remarks"></a>备注

[ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages)接口允许客户端获取对象支持的属性页的 clsid 列表。 类 `ISpecifyPropertyPagesImpl` 提供此接口的默认实现，并 `IUnknown` 通过在调试版本中将信息发送到转储设备来实现。

> [!NOTE]
> `ISpecifyPropertyPages`如果对象不支持属性页，请不要公开接口。

**相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)， [创建 atl 项目](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a> ISpecifyPropertyPagesImpl::GetPages

用可在对象的属性表中显示的属性页的 Clsid 填充 [CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid) 结构中的数组。

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>备注

ATL 使用对象的属性映射来检索每个 CLSID。

请参阅 Windows SDK 中的 [ISpecifyPropertyPages：： GetPages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) 。

## <a name="see-also"></a>请参阅

[IPropertyPageImpl 类](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl 类](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
