---
description: 了解详细信息： IPersistStreamInitImpl 类
title: IPersistStreamInitImpl 类
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: f60483435be750c7031f2e7bf7f3f18cba36a023
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158148"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl 类

此类实现 `IUnknown` 并提供 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) 接口的默认实现。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IPersistStreamInitImpl` 。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IPersistStreamInitImpl：： GetClassID](#getclassid)|检索对象的 CLSID。|
|[IPersistStreamInitImpl：： GetSizeMax](#getsizemax)|检索保存对象数据所需的流的大小。 ATL 实现返回 E_NOTIMPL。|
|[IPersistStreamInitImpl：： InitNew](#initnew)|初始化新创建的对象。|
|[IPersistStreamInitImpl：： IsDirty](#isdirty)|检查对象的数据自上次保存后是否已更改。|
|[IPersistStreamInitImpl：： Load](#load)|从指定的流加载对象的属性。|
|[IPersistStreamInitImpl：： Save](#save)|将对象的属性保存到指定的流。|

## <a name="remarks"></a>备注

[IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)接口允许客户端请求你的对象将其持久性数据加载并保存到单个流。 类 `IPersistStreamInitImpl` 提供此接口的默认实现，并 `IUnknown` 通过在调试版本中将信息发送到转储设备来实现。

**相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)， [创建 atl 项目](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ipersiststreaminitimplgetclassid"></a><a name="getclassid"></a> IPersistStreamInitImpl：： GetClassID

检索对象的 CLSID。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPersist：： GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) 。

## <a name="ipersiststreaminitimplgetsizemax"></a><a name="getsizemax"></a> IPersistStreamInitImpl：： GetSizeMax

检索保存对象数据所需的流的大小。

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>返回值

返回 E_NOTIMPL。

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPersistStreamInit：： GetSizeMax](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) 。

## <a name="ipersiststreaminitimplinitnew"></a><a name="initnew"></a> IPersistStreamInitImpl：： InitNew

初始化新创建的对象。

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPersistStreamInit：： InitNew](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) 。

## <a name="ipersiststreaminitimplisdirty"></a><a name="isdirty"></a> IPersistStreamInitImpl：： IsDirty

检查对象的数据自上次保存后是否已更改。

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IPersistStreamInit：： IsDirty](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) 。

## <a name="ipersiststreaminitimplload"></a><a name="load"></a> IPersistStreamInitImpl：： Load

从指定的流加载对象的属性。

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>备注

ATL 使用对象的属性映射来检索此信息。

请参阅 Windows SDK 中的 [IPersistStreamInit：： Load](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-load) 。

## <a name="ipersiststreaminitimplsave"></a><a name="save"></a> IPersistStreamInitImpl：： Save

将对象的属性保存到指定的流。

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>备注

ATL 使用对象的属性映射来存储此信息。

请参阅 Windows SDK 中的 [IPersistStreamInit：： Save](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-save) 。

## <a name="see-also"></a>请参阅

[存储和流](/windows/win32/Stg/storages-and-streams)<br/>
[类概述](../../atl/atl-class-overview.md)
