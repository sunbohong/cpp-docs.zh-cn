---
description: 了解详细信息：使用对话框编辑器添加控件
title: 使用对话框编辑器添加控件
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controls [MFC], adding to dialog boxes
- Dialog editor, creating controls
- common controls [MFC], adding
ms.assetid: d3f9f994-7e54-4656-a545-42c204557c36
ms.openlocfilehash: a57031539c284529b6ad21d51fd5fd2c409e2a3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314550"
---
# <a name="using-the-dialog-editor-to-add-controls"></a>使用对话框编辑器添加控件

使用 [对话框编辑器](../windows/dialog-editor.md)创建对话框模板资源时，将控件从控件调色板拖放到对话框中。 这会将该控件类型的规范添加到对话框模板资源。 构造 dialog 对象并调用其 `Create` 或 `DoModal` 成员函数时，框架会创建一个 Windows 控件，并将其放在屏幕上的对话框窗口中。

如果需要，可以改为 [手动创建控件](../mfc/adding-controls-by-hand.md) 。 这是更多的工作。

## <a name="see-also"></a>请参阅

[创建和使用控件](../mfc/making-and-using-controls.md)<br/>
[控件](../mfc/controls-mfc.md)
