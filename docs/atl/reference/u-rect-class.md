---
description: 了解详细信息： _U_RECT 类
title: _U_RECT 类
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: b3720107d1b64f930b4c64dff269de041d9b928c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157602"
---
# <a name="_u_rect-class"></a>_U_RECT 类

此参数适配器类允许 `RECT` 将指针或引用传递给在指针方面实现的函数。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class _U_RECT
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[_U_RECT：： _U_RECT](#_u_rect___u_rect)|构造函数。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[_U_RECT：： m_lpRect](#_u_rect__m_lprect)|指向的指针 `RECT` 。|

## <a name="remarks"></a>备注

类定义了两个构造函数重载：一个接受一个 **RECT&** 参数，另一个接受 `LPRECT` 参数。 第一个构造函数将引用参数的地址存储在类的单个数据成员中， [m_lpRect](#_u_rect__m_lprect)。 直接存储指针构造函数的参数而不进行转换。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a> _U_RECT：： m_lpRect

类将传递给它的任一构造函数的值作为公共 `LPRECT` 数据成员保存。

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a> _U_RECT：： _U_RECT

引用参数的地址存储在类的单个数据成员中， [m_lpRect](#_u_rect__m_lprect)。

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>parameters

*.rc*<br/>
`RECT` 引用。

*lpRect*<br/>
一个 `RECT` 指针。

### <a name="remarks"></a>备注

直接存储指针构造函数的参数而不进行转换。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
