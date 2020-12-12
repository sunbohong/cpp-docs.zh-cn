---
description: 了解详细信息： CWinTraits 类
title: CWinTraits 类
ms.date: 11/04/2016
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
ms.openlocfilehash: 3f23342cae58d70a602ebce1dcbe7efcddf36781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140083"
---
# <a name="cwintraits-class"></a>CWinTraits 类

此类提供了一个方法，用于标准化创建窗口对象时使用的样式。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>parameters

*t_dwStyle*<br/>
默认标准窗口样式。

*t_dwExStyle*<br/>
默认扩展窗口样式。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CWinTraits：： GetWndExStyle](#getwndexstyle)| (静态) 检索对象的扩展样式 `CWinTraits` 。|
|[CWinTraits：： GetWndStyle](#getwndstyle)| (静态) 检索对象的标准样式 `CWinTraits` 。|

## <a name="remarks"></a>备注

此 [窗口特征](../../atl/understanding-window-traits.md) 类提供一种简单的方法，用于标准化用于创建 ATL 窗口对象的样式。 使用此类的专用化作为 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 或 ATL 窗口类的一个模板参数，以指定用于该窗口类的实例的默认标准样式和扩展样式。

如果你希望提供默认窗口样式，而该样式仅在调用 [CWindowImpl：： Create](../../atl/reference/cwindowimpl-class.md#create)时未指定其他样式时使用，则使用此模板。

ATL 提供此模板的三个预定义特殊化，适用于常用的窗口样式组合：

- `CControlWinTraits`

   设计用于标准控制窗口。 使用以下标准样式： WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN 和 WS_CLIPSIBLINGS。 没有扩展样式。

- `CFrameWinTraits`

   专为标准框架窗口设计。 使用的标准样式包括： WS_OVERLAPPEDWINDOW、WS_CLIPCHILDREN 和 WS_CLIPSIBLINGS。 使用的扩展样式包括： WS_EX_APPWINDOW 和 WS_EX_WINDOWEDGE。

- `CMDIChildWinTraits`

   设计用于标准 MDI 子窗口。 使用的标准样式包括： WS_OVERLAPPEDWINDOW、WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN 和 WS_CLIPSIBLINGS。 使用的扩展样式包括： WS_EX_MDICHILD。

如果要确保为窗口类的所有实例设置某些样式，同时允许基于每个实例设置其他样式，请改用 [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) 。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a> CWinTraits：： GetWndStyle

调用此函数可检索对象的标准样式 `CWinTraits` 。

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>parameters

*dwStyle*<br/>
用于创建窗口的标准样式。 如果 *dwStyle* 为0，则返回)  (模板样式值 `t_dwStyle` 。 如果 *dwStyle* 为非零，则返回 *dwStyle* 。

### <a name="return-value"></a>返回值

对象的标准窗口样式。

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraits：： GetWndExStyle

调用此函数可检索对象的扩展样式 `CWinTraits` 。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>parameters

*dwExStyle*<br/>
用于创建窗口的扩展样式。 如果 *dwExStyle* 为0，则返回)  (模板样式值 `t_dwExStyle` 。 如果 *dwExStyle* 为非零，则返回 *dwExStyle* 。

### <a name="return-value"></a>返回值

对象的扩展窗口样式。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)<br/>
[了解窗口特性](../../atl/understanding-window-traits.md)
