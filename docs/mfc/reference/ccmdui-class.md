---
description: 了解详细信息： CCmdUI 类
title: CCmdUI 类
ms.date: 09/06/2019
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
ms.openlocfilehash: d868c0dc3c9915f5300f56e5bfa5f1971d4ec3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132985"
---
# <a name="ccmdui-class"></a>CCmdUI 类

仅在 `ON_UPDATE_COMMAND_UI` 派生类的处理程序中使用 `CCmdTarget` 。

## <a name="syntax"></a>语法

```
class CCmdUI
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CCmdUI：： ContinueRouting](#continuerouting)|告诉命令路由机制继续向下传递处理程序链中的当前消息。|
|[CCmdUI：： Enable](#enable)|启用或禁用此命令的用户界面项。|
|[CCmdUI：： SetCheck](#setcheck)|为此命令设置用户界面项的复选状态。|
|[CCmdUI：： SetRadio](#setradio)|与 `SetCheck` 成员函数类似，但操作的是单选组。|
|[CCmdUI：： SetText](#settext)|为此命令设置用户界面项的文本。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CCmdUI：： m_nID](#m_nid)|用户界面对象的 ID。|
|[CCmdUI：： m_nIndex](#m_nindex)|用户界面对象的索引。|
|[CCmdUI：： m_pMenu](#m_pmenu)|指向由对象表示的菜单 `CCmdUI` 。|
|[CCmdUI：： m_pOther](#m_pother)|指向发送通知的窗口对象。|
|[CCmdUI：： m_pSubMenu](#m_psubmenu)|指向由对象表示的包含的子菜单 `CCmdUI` 。|

## <a name="remarks"></a>备注

`CCmdUI` 没有基类。

当应用程序的用户下拉菜单时，每个菜单项都需要知道它是显示为已启用还是已禁用。 菜单命令的目标通过实现 ON_UPDATE_COMMAND_UI 处理程序来提供此信息。 对于应用程序中的每个命令用户界面对象，使用 [类向导](mfc-class-wizard.md) 或 " **属性** " 窗口 (**类视图**) 为每个处理程序创建消息映射项和函数原型。

当下拉菜单向下移动时，框架会搜索并调用每个 ON_UPDATE_COMMAND_UI 处理程序，每个处理程序都调用 `CCmdUI` 和等成员函数， `Enable` 然后， `Check` 框架相应地显示每个菜单项。

菜单项可以替换为控件条按钮或其他命令用户界面对象，而无需更改处理程序中的代码 `ON_UPDATE_COMMAND_UI` 。

下表总结了 `CCmdUI` 对各种命令用户界面项的影响的成员函数。

|User-Interface 项|启用|SetCheck|SetRadio|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|Menu item|启用或禁用|选中或取消选中|使用点进行检查|设置项文本|
|工具栏按钮|启用或禁用|选择、取消选择或不确定|与 `SetCheck` 相同|(ぃ続ノ)|
|状态栏窗格|使文本可见或不可见|设置弹出框或普通边框|与 `SetCheck` 相同|设置窗格文本|
|"普通" 按钮 `CDialogBar`|启用或禁用|选中或取消选中复选框|与 `SetCheck` 相同|设置按钮文本|
|正常控制 `CDialogBar`|启用或禁用|(ぃ続ノ)|(ぃ続ノ)|设置窗口文本|

有关使用此类的详细信息，请参阅 [如何更新 User-Interface 对象](../../mfc/how-to-update-user-interface-objects.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CCmdUI`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a> CCmdUI：： ContinueRouting

调用此成员函数，告诉命令路由机制继续向下传递处理程序链中的当前消息。

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>备注

这是一个高级成员函数，应与返回 FALSE 的 ON_COMMAND_EX 处理程序结合使用。 有关详细信息，请参阅 [技术说明 6](../../mfc/tn006-message-maps.md)。

## <a name="ccmduienable"></a><a name="enable"></a> CCmdUI：： Enable

调用此成员函数可以启用或禁用此命令的用户界面项。

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>parameters

*bOn*<br/>
若要启用该项，则为 TRUE; 否则为 FALSE。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a> CCmdUI：： m_nID

对象表示的菜单项、工具栏按钮或其他用户界面对象的 ID `CCmdUI` 。

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a> CCmdUI：： m_nIndex

对象表示的菜单项、工具栏按钮或其他用户界面对象的索引 `CCmdUI` 。

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a> CCmdUI：： m_pMenu

指向 `CMenu` 对象表示的菜单) 类型 (的指针 `CCmdUI` 。

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>备注

如果项不是菜单，则为 NULL。

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a> CCmdUI：： m_pSubMenu

指向由 `CMenu` 对象表示的包含的子菜单) 类型 (的指针 `CCmdUI` 。

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>备注

如果项不是菜单，则为 NULL。 如果子菜单是一个弹出窗口， *m_nID* 将包含弹出菜单中第一项的 ID。 有关详细信息，请参阅 [技术说明 21](../../mfc/tn021-command-and-message-routing.md)。

## <a name="ccmduim_pother"></a><a name="m_pother"></a> CCmdUI：： m_pOther

指针 (类型 `CWnd`) 为发送通知的窗口对象，例如工具或状态栏。

```
CWnd* m_pOther;
```

### <a name="remarks"></a>备注

如果该项是菜单或非对象，则为 NULL `CWnd` 。

## <a name="ccmduisetcheck"></a><a name="setcheck"></a> CCmdUI：： SetCheck

调用此成员函数可将此命令的用户界面项设置为相应的复选状态。

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>parameters

*n*<br/>
指定要设置的检查状态。 如果为0，则取消选中;如果为1，则检查;如果为2，则设置不确定。

### <a name="remarks"></a>备注

此成员函数适用于菜单项和工具栏按钮。 不确定状态仅适用于工具栏按钮。

## <a name="ccmduisetradio"></a><a name="setradio"></a> CCmdUI：： SetRadio

调用此成员函数可将此命令的用户界面项设置为相应的复选状态。

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>parameters

*bOn*<br/>
若要启用该项，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

此成员函数的操作类似于 `SetCheck` ，只不过它对作为单选组一部分的用户界面项进行操作。 取消选中组中的其他项不是自动的，除非这些项本身会保留单选按钮行为。

## <a name="ccmduisettext"></a><a name="settext"></a> CCmdUI：： SetText

调用此成员函数可设置此命令的用户界面项的文本。

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>parameters

*lpszText*<br/>
指向文本字符串的指针。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>请参阅

[MFC 示例 MDI](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)
