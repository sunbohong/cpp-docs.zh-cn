---
description: 了解详细信息：在 CStatusBarCtrl 对象中使用工具提示
title: 在 CStatusBarCtrl 对象中使用工具提示
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: d77610a511698000dc70a1aa1cb1edb22fb3eb7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143242"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>在 CStatusBarCtrl 对象中使用工具提示

若要为状态栏控件启用工具提示，请创建 `CStatusBarCtrl` 具有 SBT_TOOLTIPS 样式的对象。

> [!NOTE]
> 如果要使用 `CStatusBar` 对象实现状态栏，请使用 `CStatusBar::CreateEx` 函数。 它允许您为嵌入对象指定其他样式 `CStatusBarCtrl` 。

`CStatusBarCtrl`成功创建对象后，请使用[CStatusBarCtrl：： SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext)和[CStatusBarCtrl：： GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext)来设置和检索特定窗格的提示文本。

设置工具提示后，仅当部件具有图标且没有文本，或所有文本无法在部件内显示时才显示工具提示。 简单模式中不支持工具提示。

## <a name="see-also"></a>请参阅

[使用 CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
