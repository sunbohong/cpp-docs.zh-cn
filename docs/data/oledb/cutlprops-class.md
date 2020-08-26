---
title: CUtlProps 类
ms.date: 11/04/2016
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
ms.openlocfilehash: 46fa266c5a8328bbcf7cfd1257ce1ff3e38ed2bb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845661"
---
# <a name="cutlprops-class"></a>CUtlProps 类

实现多种 OLE DB 属性接口的属性，例如、、 `IDBProperties` `IDBProperties` 和 `IRowsetInfo`)  (。

## <a name="syntax"></a>语法

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>参数

*T*<br/>
包含的类 `BEGIN_PROPSET_MAP` 。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="methods"></a>方法

| 名称 | 说明 |
|-|-|
|[GetPropValue](#getpropvalue)|从属性集中获取属性。|
|[IsValidValue](#isvalidvalue)|用于在设置属性之前验证值。|
|[OnInterfaceRequested](#oninterfacerequested)|当使用者在对象创建接口上调用方法时，为可选接口处理请求。|
|[OnPropertyChanged](#onpropertychanged)|设置属性以处理链接属性后调用。|
|[SetPropValue](#setpropvalue)|设置属性集中的属性。|

## <a name="remarks"></a>注解

此类的大部分是实现详细信息。

`CUtlProps` 包含两个成员，用于内部设置属性： [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) 和 [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)。

有关在属性集映射中使用的宏的详细信息，请参阅 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) 和 [END_PROPSET_MAP](../../data/oledb/end-propset-map.md)。

## <a name="cutlpropsgetpropvalue"></a><a name="getpropvalue"></a> CUtlProps：： GetPropValue

从属性集中获取属性。

### <a name="syntax"></a>语法

```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>参数

*pguidPropSet*<br/>
中PropSet 的 GUID。

*dwPropId*<br/>
中属性索引。

*pvValue*<br/>
弄指向包含新属性值的变量的指针。

### <a name="return-value"></a>返回值

`Failure` 如果失败，S_OK 成功。

## <a name="cutlpropsisvalidvalue"></a><a name="isvalidvalue"></a> CUtlProps：： IsValidValue

用于在设置属性之前验证值。

### <a name="syntax"></a>语法

```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>参数

*iCurSet*<br/>
属性集数组中的索引;如果仅有一个属性集，则为零。

*pDBProp*<br/>
[DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85))结构中的属性 ID 和新值。

### <a name="return-value"></a>返回值

标准的 HRESULT。 默认的返回值为 S_OK。

### <a name="remarks"></a>注解

如果要在要用于设置属性的值上运行任何验证例程，则应重写此函数。 例如，可以根据密码表验证 DBPROP_AUTH_PASSWORD 来确定有效值。

## <a name="cutlpropsoninterfacerequested"></a><a name="oninterfacerequested"></a> CUtlProps：： OnInterfaceRequested

当使用者在某个对象创建接口上调用方法时，为该接口处理请求。

### <a name="syntax"></a>语法

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>参数

*riid*<br/>
中请求的接口的 IID。 有关更多详细信息，请参阅*riid* `ICommand::Execute` *MDAC SDK*) 中*OLE DB 程序员参考* (中的 riid 参数说明。

### <a name="remarks"></a>注解

`OnInterfaceRequested` 当使用者在某个对象创建 (接口（如 `IDBCreateSession` 、 `IDBCreateCommand` 、 `IOpenRowset` 或) ）上调用方法时，处理对可选接口的使用者请求 `ICommand` 。 它为请求的接口设置相应的 OLE DB 属性。 例如，如果使用者请求，则会 `IID_IRowsetLocate` `OnInterfaceRequested` 设置 `DBPROP_IRowsetLocate` 接口。 这样做会在创建行集期间保持正确的状态。

当使用者调用或时，将调用此方法 `IOpenRowset::OpenRowset` `ICommand::Execute` 。

如果使用者打开对象并请求一个可选接口，则提供程序应将与该接口关联的属性设置为 VARIANT_TRUE。 若要允许特定于属性的处理，请在 `OnInterfaceRequested` 调用提供程序的方法之前调用 `Execute` 。 默认情况下， `OnInterfaceRequested` 将处理以下接口：

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

如果要处理其他接口，请在数据源、会话、命令或行集类中重写此函数以处理函数。 重写应通过常规 set/get properties 接口，以确保设置属性还设置任何链接的属性 (参阅 [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)) 。

## <a name="cutlpropsonpropertychanged"></a><a name="onpropertychanged"></a> CUtlProps：： OnPropertyChanged

设置属性以处理链接属性后调用。

### <a name="syntax"></a>语法

```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>参数

*iCurSet*<br/>
属性集数组中的索引;如果仅有一个属性集，则为零。

*pDBProp*<br/>
[DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85))结构中的属性 ID 和新值。

### <a name="return-value"></a>返回值

标准的 HRESULT。 默认的返回值为 S_OK。

### <a name="remarks"></a>注解

如果要处理链接的属性（如书签或更新的值依赖于其他属性的值），则应重写此函数。

### <a name="example"></a>示例

在此函数中，用户从参数获取属性 ID `DBPROP*` 。 现在，可以将 ID 与属性进行比较，使其与链相比较。 如果找到该属性， `SetProperties` 则会调用，其属性将立即与其他属性一起设置。 在这种情况下，如果一个获取 `DBPROP_IRowsetLocate` 、 `DBPROP_LITERALBOOKMARKS` 或 `DBPROP_ORDEREDBOOKMARKS` 属性，可以设置 `DBPROP_BOOKMARKS` 属性。

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="cutlpropssetpropvalue"></a><a name="setpropvalue"></a> CUtlProps：： SetPropValue

设置属性集中的属性。

### <a name="syntax"></a>语法

```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>参数

*pguidPropSet*<br/>
中PropSet 的 GUID。

*dwPropId*<br/>
中属性索引。

*pvValue*<br/>
中指向包含新属性值的变量的指针。

### <a name="return-value"></a>返回值

`Failure` 如果失败，S_OK 成功。

## <a name="see-also"></a>另请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
