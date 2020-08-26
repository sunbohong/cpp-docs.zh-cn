---
title: CMFCDisableMenuAnimation 类
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: 97a93e000b3e12d8ec4824100059581216b1b8d9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840760"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation 类

禁用弹出菜单动画。

## <a name="syntax"></a>语法

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|说明|
|-|-|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|构造 `CMFCDisableMenuAnimation` 对象。|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|说明|
|-|-|
|[CMFCDisableMenuAnimation：： Restore](#restore)|还原框架用于显示弹出菜单的以前的动画。|

### <a name="data-members"></a>数据成员

|名称|说明|
|-|-|
|`CMFCDisableMenuAnimation::m_animType`|存储上一个弹出菜单动画类型。|

### <a name="remarks"></a>注解

使用此帮助器类可暂时禁用弹出菜单动画 (例如，在处理鼠标或键盘命令) 时。

`CMFCDisableMenuAnimation`对象在其生存期内禁用弹出菜单动画。 构造函数将当前的弹出菜单动画类型存储在字段中 `m_animType` ，并将当前的动画类型设置为 `CMFCPopupMenu::NO_ANIMATION` 。 析构函数将还原以前的动画类型。

您可以 `CMFCDisableMenuAnimation` 在堆栈上创建一个对象，以禁用整个单个函数的弹出菜单动画。 如果要禁用函数之间的弹出菜单动画，请 `CMFCDisableMenuAnimation` 在该堆上创建一个对象，并在需要还原弹出菜单动画时将其删除。

## <a name="example"></a>示例

下面的示例演示如何使用堆栈暂时禁用菜单动画。

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>要求

**标头：** afxpopupmenu

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a> CMFCDisableMenuAnimation：： Restore

还原框架用于显示弹出菜单的以前的动画。

```cpp
void Restore ();
```

### <a name="remarks"></a>注解

析构函数调用此方法 `CMFCDisableMenuAnimation` 来还原框架用于显示弹出菜单的以前的动画。

## <a name="see-also"></a>另请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu 类](../../mfc/reference/cmfcpopupmenu-class.md)
