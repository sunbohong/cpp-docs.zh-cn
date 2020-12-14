---
description: 了解更多：使用热键控件
title: 使用热键控件
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
ms.openlocfilehash: 078cd4b3d4746723d5996959edad20dd44e9abec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202699"
---
# <a name="using-a-hot-key-control"></a>使用热键控件

热键控件的典型用法遵循下面的模式：

- 创建滑块控件。 如果滑块控件是在对话框模板中指定的，则在创建对话框时自动进行创建。  (应在对话框类中具有与热键控件对应的 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) 成员。 ) 或者，你可以使用 [create](../mfc/reference/chotkeyctrl-class.md#create) member 函数将控件创建为任何窗口的子窗口。

- 如果要为控件设置默认值，请调用 [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) 成员函数。 如果要禁止某些移位状态，请调用 [指向](../mfc/reference/chotkeyctrl-class.md#setrules)。 对于对话框中的控件，可以在对话框的 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 函数中执行此操作。

- 当热键控件有焦点时，用户通过按热键组合与控件进行交互。 然后，用户可以通过单击对话框中的按钮来指示此任务已完成。

- 当系统通知你用户已选择热键时，它应使用成员函数 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) 来检索热键控件中的虚拟键和移位状态值。

- 知道用户选择的密钥后，可以使用 [设置热键](../mfc/setting-a-hot-key.md)中所述的方法之一设置热键。

- 如果热键控件位于对话框中，则它和 `CHotKeyCtrl` 对象将自动被销毁。 否则，您需要确保正确地销毁控件和 `CHotKeyCtrl` 对象。

## <a name="see-also"></a>请参阅

[使用 CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
