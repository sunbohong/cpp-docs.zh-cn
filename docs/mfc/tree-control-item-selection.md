---
description: 了解详细信息：树控件项选择
title: 树控件项选择
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: 46e1256eea3e8175b996a1b6bdfdd7c1de2739d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264032"
---
# <a name="tree-control-item-selection"></a>树控件项选择

当所选内容从一项更改为另一项时，树控件 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 发送 [TVN_SELCHANGING](/windows/win32/Controls/tvn-selchanging) 和 [TVN_SELCHANGED](/windows/win32/Controls/tvn-selchanged) 通知消息。 这两个通知包括指定更改是鼠标单击还是击键的结果的值。 通知还包括有关将获取选择的项和将失去选择的项的信息。 您可以使用此信息设置依赖项的选择状态的项特性。 在响应中返回 **TRUE** 以 `TVN_SELCHANGING` 阻止选择更改; 如果返回 **FALSE** ，则允许更改。

应用程序可以通过调用 [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) 成员函数来更改选择。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)
