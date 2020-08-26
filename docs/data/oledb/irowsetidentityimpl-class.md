---
title: IRowsetIdentityImpl 类
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: 48ed687ff67208109b5a2acf400d98491b4c769a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836138"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl 类

实现 OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85)) 接口，该接口启用行标识测试。

## <a name="syntax"></a>语法

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>参数

*T*<br/>
派生自的类 `IRowsetIdentityImpl` 。

*RowClass*<br/>
的存储单元 `HROW` 。

## <a name="requirements"></a>要求

**标头：** atldb.h

## <a name="members"></a>成员

### <a name="methods"></a>方法

| 名称 | 说明 |
|-|-|
|[IsSameRow](#issamerow)|比较两个行句柄，以确定它们是否引用相同的行。|

## <a name="irowsetidentityimplissamerow"></a><a name="issamerow"></a> IRowsetIdentityImpl：： IsSameRow

比较两个行句柄，以确定它们是否引用相同的行。

### <a name="syntax"></a>语法

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[IRowsetIdentity：： IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) 。

### <a name="remarks"></a>注解

为了比较行句柄，此方法会将 `HROW` 句柄转换为 `RowClass` 成员，并调用 `memcmp` 指针。

## <a name="see-also"></a>另请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
