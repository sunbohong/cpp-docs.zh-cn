---
description: 了解详细信息： CWinTraitsOR 类
title: CWinTraitsOR 类
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: 1d0a7ff8a78ebbdc416bdace2a1ea1f0199c292f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140057"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR 类

此类提供了一个方法，用于标准化创建窗口对象时使用的样式。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>parameters

*t_dwStyle*<br/>
默认窗口样式。

*t_dwExStyle*<br/>
默认扩展窗口样式。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|检索对象的扩展样式 `CWinTraitsOR` 。|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|检索对象的标准样式 `CWinTraitsOR` 。|

## <a name="remarks"></a>备注

此 [窗口特征](../../atl/understanding-window-traits.md) 类提供一种简单的方法，用于标准化用于创建 ATL 窗口对象的样式。 使用此类的专用化作为 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 或 ATL 窗口类的一个模板参数，以指定用于该窗口类的实例的标准和扩展样式的最小集。

如果要确保为窗口类的所有实例设置某些样式，同时允许在调用 [CWindowImpl：： Create](../../atl/reference/cwindowimpl-class.md#create)时为每个实例设置其他样式，请使用此模板的专用化。

如果你希望提供默认窗口样式，该样式将仅在对的调用中未指定其他样式时使用 `CWindowImpl::Create` ，请改用 [CWinTraits](../../atl/reference/cwintraits-class.md) 。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a> CWinTraitsOR::GetWndStyle

调用此函数可检索组合 (使用对象的标准样式的逻辑或运算符) `CWinTraits` 和 *t_dwStyle* 指定的默认样式。

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>parameters

*dwStyle*<br/>
用于创建窗口的样式。

### <a name="return-value"></a>返回值

使用逻辑 OR 运算符传递到 *dwStyle* 中的样式和由指定的默认样式组合 `t_dwStyle` 。

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraitsOR::GetWndExStyle

调用此函数可检索组合 (使用对象扩展样式的逻辑或运算符) `CWinTraits` 和指定的默认样式 `t_dwStyle` 。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>parameters

*dwExStyle*<br/>
用于创建窗口的扩展样式。

### <a name="return-value"></a>返回值

 `t_dwExStyle` 使用逻辑 OR 运算符传递到 dwExStyle 和默认值中的扩展样式的组合

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)<br/>
[了解窗口特性](../../atl/understanding-window-traits.md)
