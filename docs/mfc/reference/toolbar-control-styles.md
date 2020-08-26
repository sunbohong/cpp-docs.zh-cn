---
title: 工具栏控件样式
ms.date: 11/04/2016
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
ms.openlocfilehash: eab4dbde68fcebdb0afd0d058b4678c464874c81
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837120"
---
# <a name="toolbar-control-styles"></a>工具栏控件样式

[CMFCToolBarButton 类](../../mfc/reference/cmfctoolbarbutton-class.md) 具有一组样式标志，这些标志确定按钮的外观和行为。 可以通过调用 [CMFCToolBarButton：： system.windows.forms.control.setstyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)来设置这些标志的组合。 本主题列出了样式标志值及其含义。

## <a name="property-values"></a>属性值

下列值确定控件表示的按钮的类型：

|名称|说明|
|-|-|
|TBBS_BUTTON|标准按键（默认）。  |
|TBBS_CHECKBOX|复选框  |
|TBBS_CHECKGROUP|复选框组的开始。  |
|TBBS_GROUP|按钮组的开始。  |
|TBBS_SEPARATOR|分隔符。  |

下列值表示控件的当前状态：

|名称|说明|
|-|-|
|TBBS_CHECKED|复选框处于选中状态。  |
|TBBS_DISABLED|控件已禁用。  |
|TBBS_INDETERMINATE|复选框处于不确定状态。  |
|TBBS_PRESSED|按钮处于按下状态。  |

下列值将更改按钮在工具栏中的布局：

|名称|说明|
|-|-|
|TBBS_BREAK|将项放置在新行或新列上，无需分隔列。  |

## <a name="remarks"></a>注解

当前样式存储在 [CMFCToolBarButton：： m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)中。 不要直接在中设置新值                 `m_nStyle` ，因为某些派生类在调用时执行附加处理 `SetStyles` 。

视觉管理器将确定按钮在每种状态下的外观。 有关详细信息，请参阅 [可视化管理器](../../mfc/visualization-manager.md) 。

## <a name="requirements"></a>要求

**标头：** afxtoolbarbutton

## <a name="see-also"></a>另请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CMFCToolBarButton 类](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[可视化管理器](../../mfc/visualization-manager.md)
