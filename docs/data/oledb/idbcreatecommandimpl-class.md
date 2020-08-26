---
title: IDBCreateCommandImpl 类
ms.date: 11/04/2016
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- IDBCreateCommandImpl::CreateCommand
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
ms.openlocfilehash: b7b658b2b365eb84a39ae94cef7c77e18d7bd4a0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845544"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl 类

提供 [IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85)) 接口的实现。

## <a name="syntax"></a>语法

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>参数

*T*<br/>
派生自的会话对象 `IDBCreateCommandImpl` 。

*CommandClass*<br/>
Command 类。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="interface-methods"></a>接口方法

| 名称 | 说明 |
|-|-|
|[CreateCommand](#createcommand)|创建新的命令。|

## <a name="remarks"></a>注解

用于获取新命令的 session 对象上的可选接口。

## <a name="idbcreatecommandimplcreatecommand"></a><a name="createcommand"></a> IDBCreateCommandImpl：： CreateCommand

创建新的命令并返回所请求的接口。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[IDBCreateCommand：： CreateCommand](/previous-versions/windows/desktop/ms709772(v=vs.85)) 。

一些参数对应于不同名称 *OLE DB 程序员引用* 参数，如中所述 `IDBCreateCommand::CreateCommand` ：

|OLE DB 模板参数|*OLE DB 程序员引用* 参数|
|--------------------------------|------------------------------------------------|
|*ppvCommand*|*ppCommand*|

## <a name="see-also"></a>另请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
