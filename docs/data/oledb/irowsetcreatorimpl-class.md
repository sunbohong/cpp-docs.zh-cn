---
title: IRowsetCreatorImpl 类
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
ms.openlocfilehash: c1ad2c5e97dfe975a3b545e44b512dff7bf512a0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843439"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl 类

执行与相同的函数， `IObjectWithSite` 但同时启用 OLE DB 属性 `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` 。

## <a name="syntax"></a>语法

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>参数

*T*<br/>
派生自的类 `IRowsetCreator` 。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="methods"></a>方法

| 名称 | 说明 |
|-|-|
|[SetSite](#setsite)|设置包含行集对象的站点。|

## <a name="remarks"></a>注解

此类继承自 [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) ，并重写 [IObjectWithSite：： SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)。 当提供程序命令或会话对象创建行集时，它会对 `QueryInterface` 查找 `IObjectWithSite` 并调用将 `SetSite` 行集对象的 `IUnkown` 接口作为站点接口传递的行集对象调用。

## <a name="irowsetcreatorimplsetsite"></a><a name="setsite"></a> IRowsetCreatorImpl：： SetSite

设置包含行集对象的站点。 有关详细信息，请参阅 [IObjectWithSite：： SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>参数

*pCreator*<br/>
中指向 `IUnknown` 管理行集对象的站点的接口指针的指针。

### <a name="return-value"></a>返回值

标准的 HRESULT。

### <a name="remarks"></a>注解

此外，还 `IRowsetCreatorImpl::SetSite` 将启用 OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` 属性。

## <a name="see-also"></a>另请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
