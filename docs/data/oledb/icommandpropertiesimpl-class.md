---
description: 了解详细信息： ICommandPropertiesImpl 类
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
ms.openlocfilehash: bf6a6f9a3ddd43a61671a85a791d63958f63c3e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317555"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl 类

提供 [ICommandProperties](/previous-versions/windows/desktop/ms723044(v=vs.85)) 接口的实现。

## <a name="syntax"></a>语法

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>parameters

*T*<br/>
你的类，派生自

*PropClass*<br/>
Properties 类。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="interface-methods"></a>接口方法

| 名称 | 描述 |
|-|-|
|[GetProperties](#getproperties)|返回行集属性组中当前为行集请求的属性的列表。|
|[SetProperties](#setproperties)|设置行集属性组中的属性。|

## <a name="remarks"></a>备注

这对于命令是必需的。 实现由 [BEGIN_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#begin_propset_map) 宏定义的静态函数提供。

## <a name="icommandpropertiesimplgetproperties"></a><a name="getproperties"></a> ICommandPropertiesImpl：： GetProperties

使用命令的属性映射返回所有请求的属性集。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>parameters

请参阅 *OLE DB 程序员参考* 中的 [ICommandProperties：： GetProperties](/previous-versions/windows/desktop/ms723119(v=vs.85)) 。

### <a name="remarks"></a>备注

请参阅 [BEGIN_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#begin_propset_map)。

## <a name="icommandpropertiesimplsetproperties"></a><a name="setproperties"></a> ICommandPropertiesImpl：： SetProperties

设置命令对象的属性。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>parameters

请参阅 *OLE DB 程序员参考* 中的 [ICommandProperties：： SetProperties](/previous-versions/windows/desktop/ms711497(v=vs.85)) 。

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
