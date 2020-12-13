---
description: 了解详细信息： _U_STRINGorID 类
title: _U_STRINGorID 类
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: bbbf3d32e86d035344ba8d3dcd60c4ebe66d9c3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138757"
---
# <a name="_u_stringorid-class"></a>_U_STRINGorID 类

此参数适配器类允许 (的资源名称) 或资源 Id (UINTs) 传递到函数，而无需调用方使用 MAKEINTRESOURCE 宏将 ID 转换为字符串。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class _U_STRINGorID
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[_U_STRINGorID：： _U_STRINGorID](#_u_stringorid___u_stringorid)|构造函数。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[_U_STRINGorID：： m_lpstr](#_u_stringorid__m_lpstr)|资源标识符。|

## <a name="remarks"></a>备注

此类用于实现 Windows 资源管理 API 的包装器，例如 [system.windows.frameworkelement.findresource](/windows/win32/api/winbase/nf-winbase-findresourcea)、 [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)和 [LoadMenu](/windows/win32/api/winuser/nf-winuser-loadmenuw) 函数，这些函数接受一个 LPCTSTR 参数，该参数可以是资源名称或其 ID。

类定义了两个构造函数重载：一个接受 LPCTSTR 参数，另一个接受 UINT 参数。 UINT 参数转换为与 Windows 资源管理函数兼容的资源类型，使用 MAKEINTRESOURCE 宏和存储在类的单个数据成员中的结果 [m_lpstr](#_u_stringorid__m_lpstr)。 无需转换即可直接存储 LPCTSTR 构造函数的参数。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="_u_stringoridm_lpstr"></a><a name="_u_stringorid__m_lpstr"></a> _U_STRINGorID：： m_lpstr

类将传递给它的任一构造函数的值保存为公共 LPCTSTR 数据成员。

```
LPCTSTR m_lpstr;
```

## <a name="_u_stringorid_u_stringorid"></a><a name="_u_stringorid___u_stringorid"></a> _U_STRINGorID：： _U_STRINGorID

UINT 构造函数将其参数转换为与使用 MAKEINTRESOURCE 宏的 Windows 资源管理函数兼容的资源类型，并将结果存储在类的单个数据成员 [m_lpstr](#_u_stringorid__m_lpstr)中。

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>parameters

*nID*<br/>
资源 ID。

*lpString*<br/>
资源名称。

### <a name="remarks"></a>备注

无需转换即可直接存储 LPCTSTR 构造函数的参数。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
