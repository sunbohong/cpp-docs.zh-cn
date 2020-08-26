---
title: IDBInitializeImpl 类
ms.date: 11/04/2016
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
ms.openlocfilehash: aff02e812d2806201a08164aeb4a8ef290550725
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845531"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl 类

提供 [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85)) 接口的实现。

## <a name="syntax"></a>语法

```cpp
template <class T>
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize
```

### <a name="parameters"></a>参数

*T*<br/>
派生自的类 `IDBInitializeImpl` 。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="methods"></a>方法

| 名称 | 说明 |
|-|-|
|[IDBInitializeImpl](#idbinitializeimpl)|构造函数。|

### <a name="interface-methods"></a>接口方法

| 名称 | 说明 |
|-|-|
|[初始化](#initialize)|启动提供程序。|
|[撤消](#uninitialize)|停止提供程序。|

### <a name="data-members"></a>数据成员

| 名称 | 说明 |
|-|-|
|[m_dwStatus](#dwstatus)|数据源标志。|
|[m_pCUtlPropInfo](#pcutlpropinfo)|指向 DB 属性信息的实现的指针。|

## <a name="remarks"></a>注解

数据源对象上的必需接口和枚举器上的可选接口。

## <a name="idbinitializeimplidbinitializeimpl"></a><a name="idbinitializeimpl"></a> IDBInitializeImpl：： IDBInitializeImpl

构造函数。

### <a name="syntax"></a>语法

```cpp
IDBInitializeImpl();
```

### <a name="remarks"></a>备注

初始化所有数据成员。

## <a name="idbinitializeimplinitialize"></a><a name="initialize"></a> IDBInitializeImpl：： Initialize

通过准备数据源对象的属性支持来初始化该对象。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(Initialize)(void);
```

### <a name="remarks"></a>备注

请参阅*OLE DB 程序员参考*中的[IDBInitialize：： Initialize](/previous-versions/windows/desktop/ms718026(v=vs.85)) 。

## <a name="idbinitializeimpluninitialize"></a><a name="uninitialize"></a> IDBInitializeImpl：：取消初始化

通过释放内部资源（如属性支持），使数据源对象处于未初始化状态。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(Uninitialize)(void);
```

### <a name="remarks"></a>备注

请参阅*OLE DB 程序员参考*中的[IDBInitialize：：](/previous-versions/windows/desktop/ms719648(v=vs.85))取消。

## <a name="idbinitializeimplm_dwstatus"></a><a name="dwstatus"></a> IDBInitializeImpl：： m_dwStatus

数据源标志。

### <a name="syntax"></a>语法

```cpp
DWORD m_dwStatus;
```

### <a name="remarks"></a>备注

这些标志指定或指明数据源对象的各种属性的状态。 包含一个或多个以下 **`enum`** 值：

```cpp
enum DATASOURCE_FLAGS {
    DSF_MASK_INIT     = 0xFFFFF00F,
    DSF_PERSIST_DIRTY = 0x00000001,
    DSF_INITIALIZED   = 0x00000010,
};
```

| 值 | 说明 |
|-|-|
|`DSF_MASK_INIT`|用于启用未初始化状态还原的掩码。|
|`DSF_PERSIST_DIRTY`|设置数据源对象是否需要持久性 (也就是说，如果已更改) 。|
|`DSF_INITIALIZED`|设置数据源是否已初始化。|

## <a name="idbinitializeimplm_pcutlpropinfo"></a><a name="pcutlpropinfo"></a> IDBInitializeImpl：： m_pCUtlPropInfo

指向 DB 属性信息的实现对象的指针。

### <a name="syntax"></a>语法

```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;
```

## <a name="see-also"></a>另请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
