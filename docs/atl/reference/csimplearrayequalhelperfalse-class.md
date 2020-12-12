---
description: 了解详细信息： CSimpleArrayEqualHelperFalse 类
title: CSimpleArrayEqualHelperFalse 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 196f7873f72799408a629bc784cb343966801d79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140720"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse 类

此类是 [CSimpleArray](../../atl/reference/csimplearray-class.md) 类的帮助器。

## <a name="syntax"></a>语法

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生类。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse：： IsEqual](#isequal)| (Static) 返回 false。|

## <a name="remarks"></a>备注

此特征类是对类的补充 `CSimpleArray` 。 它始终返回 false，此外， `ATLASSERT` 如果曾引用参数，则将使用参数 false 调用。 在未充分定义相等性测试的情况下，此类允许包含元素的数组对大多数方法正确运行，但对于依赖于比较（如 [CSimpleArray：： Find](../../atl/reference/csimplearray-class.md#find)）的方法，这些方法会以定义完善的方式进行操作。

## <a name="requirements"></a>要求

**标头：** atlsimpcoll

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelperFalse：： IsEqual

返回 false。

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>返回值

返回 false。

### <a name="remarks"></a>备注

此方法始终返回 false，并将 `ATLASSERT` 使用参数 false （如果被引用）调用。 的目的 `CSimpleArrayEqualHelperFalse::IsEqual` 是在没有充分定义相等性测试的情况时使用比较来强制使用比较来失败。

## <a name="see-also"></a>请参阅

[CSimpleArrayEqualHelper 类](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
