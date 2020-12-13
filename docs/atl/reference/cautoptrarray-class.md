---
description: 了解详细信息： CAutoPtrArray 类
title: CAutoPtrArray 类
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 55f9382c82a1e242342d0d740c369a571c43f9ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152570"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray 类

此类提供在构造智能指针数组时有用的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```cpp
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

### <a name="parameters"></a>parameters

*E*<br/>
指针类型。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|构造函数。|

## <a name="remarks"></a>备注

此类提供构造函数并从 [CAtlArray](../../atl/reference/catlarray-class.md) 和 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) 派生方法，以帮助创建存储智能指针的集合类对象。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a> CAutoPtrArray::CAutoPtrArray

构造函数。

```cpp
CAutoPtrArray() throw();
```

### <a name="remarks"></a>备注

初始化智能指针数组。

## <a name="see-also"></a>请参阅

[CAtlArray 类](../../atl/reference/catlarray-class.md)<br/>
[CAutoPtrElementTraits 类](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[CAutoPtrList 类](../../atl/reference/cautoptrlist-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
