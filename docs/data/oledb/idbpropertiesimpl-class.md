---
description: 了解详细信息： IDBPropertiesImpl 类
title: IDBPropertiesImpl 类
ms.date: 11/04/2016
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- IDBPropertiesImpl::SetProperties
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
ms.openlocfilehash: e8384086de5b61422cd63e2dc3fbda0cfe040843
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317488"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl 类

提供接口的实现 `IDBProperties` 。

## <a name="syntax"></a>语法

```cpp
template <class T>
class ATL_NO_VTABLE IDBPropertiesImpl
   : public IDBProperties, public CUtlProps<T>
```

### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IDBPropertiesImpl` 。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="interface-methods"></a>接口方法

| 名称 | 描述 |
|-|-|
|[GetProperties](#getproperties)|返回当前在数据源对象上设置的数据源、数据源信息和初始化属性组中的属性值，或当前在枚举器上设置的初始化属性组中的属性值。|
|[GetPropertyInfo](#getpropertyinfo)|返回有关提供程序支持的所有属性的信息。|
|[SetProperties](#setproperties)|为枚举器的数据源对象和初始化属性组、数据源对象或初始化属性组设置属性。|

## <a name="remarks"></a>备注

[IDBProperties](/previous-versions/windows/desktop/ms719607(v=vs.85)) 是数据源对象的必需接口和枚举器的可选接口。 但是，如果枚举器公开 [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85))，则它必须公开 `IDBProperties` 。 `IDBPropertiesImpl``IDBProperties`使用[BEGIN_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#begin_propset_map)定义的静态函数实现。

## <a name="idbpropertiesimplgetproperties"></a><a name="getproperties"></a> IDBPropertiesImpl：： GetProperties

返回当前在数据源对象上设置的数据源、数据源信息和初始化属性组中的属性值，或当前在枚举器上设置的初始化属性组中的属性值。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcProperties,
   DBPROPSET ** prgProperties);
```

#### <a name="parameters"></a>parameters

请参阅 *OLE DB 程序员参考* 中的 [IDBProperties：： GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) 。

一些参数对应于不同名称 *OLE DB 程序员引用* 参数，如中所述 `IDBProperties::GetProperties` ：

|OLE DB 模板参数|*OLE DB 程序员引用* 参数|
|--------------------------------|------------------------------------------------|
|cPropertySets |*cPropertyIDSets*|
|rgPropertySets |*rgPropertyIDSets*|
|*pcProperties*|*pcPropertySets*|
|*prgProperties*|*prgPropertySets*|

### <a name="remarks"></a>备注

如果提供程序已初始化，则此方法将返回当前在数据源对象上设置的 DBPROPSET_DATASOURCE DBPROPSET_DATASOURCEINFO DBPROPSET_DBINIT 属性组中的属性值。 如果提供程序未初始化，则仅返回 DBPROPSET_DBINIT 的组属性。

## <a name="idbpropertiesimplgetpropertyinfo"></a><a name="getpropertyinfo"></a> IDBPropertiesImpl：： GetPropertyInfo

返回数据源支持的属性信息。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcPropertyInfoSets,
   DBPROPINFOSET ** prgPropertyInfoSets,
   OLECHAR ** ppDescBuffer);
```

#### <a name="parameters"></a>parameters

请参阅 *OLE DB 程序员参考* 中的 [IDBProperties：： GetPropertyInfo](/previous-versions/windows/desktop/ms718175(v=vs.85)) 。

一些参数对应于不同名称 *OLE DB 程序员引用* 参数，如中所述 `IDBProperties::GetPropertyInfo` ：

|OLE DB 模板参数|*OLE DB 程序员引用* 参数|
|--------------------------------|------------------------------------------------|
|cPropertySets |*cPropertyIDSets*|
|rgPropertySets |*rgPropertyIDSets*|

### <a name="remarks"></a>备注

使用 [IDBInitializeImpl：： m_pCUtlPropInfo](./idbinitializeimpl-class.md#pcutlpropinfo) 实现此功能。

## <a name="idbpropertiesimplsetproperties"></a><a name="setproperties"></a> IDBPropertiesImpl：： SetProperties

为枚举器的数据源对象和初始化属性组、数据源对象或初始化属性组设置属性。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>parameters

请参阅 *OLE DB 程序员参考* 中的 [IDBProperties：： SetProperties](/previous-versions/windows/desktop/ms723049(v=vs.85)) 。

### <a name="remarks"></a>备注

如果提供程序已初始化，则此方法将设置数据源对象的 DBPROPSET_DATASOURCE、DBPROPSET_DATASOURCEINFO DBPROPSET_DBINIT 属性组中的属性值。 如果访问接口未初始化，则仅设置 DBPROPSET_DBINIT 组属性。

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
