---
description: 了解详细信息：创建扩展组合框控件
title: 创建扩展组合框控件
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: 93b4a24cfe4bf191e092d2456c5b6a62f79acc78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309974"
---
# <a name="creating-an-extended-combo-box-control"></a>创建扩展组合框控件

如何创建扩展组合框控件取决于您是在对话框中使用控件，还是在非对话框窗口中创建控件。

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>直接在对话框中使用 CComboBoxEx

1. 在对话框编辑器中，将扩展组合框控件添加到对话框模板资源。 指定其控件 ID。

1. 使用扩展组合框控件的 "属性" 对话框指定所需的任何样式。

1. 使用 " [添加成员变量向导](../ide/adding-a-member-variable-visual-cpp.md) " 可使用 Control 属性添加类型为 [CComboBoxEx](reference/ccomboboxex-class.md) 的成员变量。 您可以使用此成员调用 `CComboBoxEx` 成员函数。

1. 使用 " [类向导](reference/mfc-class-wizard.md) " 可在对话框类中映射处理程序函数，该对话框用于处理 (请参阅将 [消息映射到](reference/mapping-messages-to-functions.md)) 的函数。

1. 在 [OnInitDialog](reference/cdialog-class.md#oninitdialog)中，为对象设置任何其他样式 `CComboBoxEx` 。

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>在非对话框窗口中使用 CComboBoxEx

1. 在视图或窗口类中定义控件。

1. 调用控件的 [Create](reference/ctabctrl-class.md#create) 成员函数，该函数可能在 [OnInitialUpdate](reference/cview-class.md#oninitialupdate)中，可能早于父窗口的 [OnCreate](reference/cwnd-class.md#oncreate) 处理程序函数。 设置控件的样式。

## <a name="see-also"></a>请参阅

[使用 CComboBoxEx](using-ccomboboxex.md)<br/>
[控件](controls-mfc.md)
