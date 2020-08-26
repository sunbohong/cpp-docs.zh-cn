---
title: ICommandPropertiesImpl 类
ms.date: 11/04/2016
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
ms.openlocfilehash: f71ca7f5fb675916c9db7e5720e6c148f2131351
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845570"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl 类

提供 [ICommandProperties](/previous-versions/windows/desktop/ms723044(v=vs.85)) 接口的实现。

## <a name="syntax"></a>语法

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>参数

*T*<br/>
你的类，派生自

*PropClass*<br/>
Properties 类。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="interface-methods"></a>接口方法

| 名称 | 说明 |
|-|-|
|[GetProperties](#getproperties)|返回行集属性组中当前为行集请求的属性的列表。|
|[SetProperties](#setproperties)|设置行集属性组中的属性。|

## <a name="remarks"></a>注解

这对于命令是必需的。 实现由 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) 宏定义的静态函数提供。

## <a name="icommandpropertiesimplgetproperties"></a><a name="getproperties"></a> ICommandPropertiesImpl：： GetProperties

使用命令的属性映射返回所有请求的属性集。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[ICommandProperties：： GetProperties](/previous-versions/windows/desktop/ms723119(v=vs.85)) 。

### <a name="remarks"></a>注解

请参阅 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)。

## <a name="icommandpropertiesimplsetproperties"></a><a name="setproperties"></a> ICommandPropertiesImpl：： SetProperties

设置命令对象的属性。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[ICommandProperties：： SetProperties](/previous-versions/windows/desktop/ms711497(v=vs.85)) 。

## <a name="see-also"></a>另请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
