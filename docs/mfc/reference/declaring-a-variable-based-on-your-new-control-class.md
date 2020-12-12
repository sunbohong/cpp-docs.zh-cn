---
description: 了解有关以下内容的详细信息：声明基于新控件类的变量
title: 声明基于新控件类的变量
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: aa38a38b3113e4c4826756b020860d79e03ef16b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220222"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>声明基于新控件类的变量

创建 MFC 控件类后，可以基于它声明一个变量。 若要为新变量提供上下文，必须打开对话框编辑器，然后编辑要在其中使用可重用控件的对话框。 此外，该对话框必须已有一个与其关联的类。 有关使用对话框编辑器的信息，请参阅 [对话框编辑器](../../windows/dialog-editor.md)。

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>基于可重用类声明变量

1. 编辑此对话框时，将控件从 "控件" 工具栏拖动到对话框中，将与新控件的基类相同的控件拖到该对话框中。

1. 将鼠标指针置于拖放的控件上。

1. 按住 CTRL 键的同时双击控件。

   此时将显示 " [添加成员变量](../../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard) " 对话框。

1. 在 " **访问权限** " 框中，为控件选择正确的访问权限。

1. 单击 " **控制变量** " 复选框。

1. 在 " **变量名称** " 框中，键入名称。

1. 在 " **类别**" 下，单击 " **控件**"。

1. 在 " **控件 ID** " 列表中，选择所添加的控件。 **变量类型** 列表应显示正确的变量类型，并且 "**控件类型**" 框应显示正确的控件类型。

1. 在 " **注释** " 框中，添加你想要在代码中显示的任何注释。

1. 单击 **“确定”** 。

## <a name="see-also"></a>请参阅

[将消息映射到函数](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[用代码向导添加功能](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[添加类](../../ide/adding-a-class-visual-cpp.md)<br/>
[添加成员函数](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[添加成员变量](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[重写虚函数](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 消息处理程序](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[导航类结构](../../ide/navigate-code-cpp.md)
