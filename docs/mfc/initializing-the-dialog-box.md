---
description: 了解详细信息：初始化对话框
title: 初始化对话框
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 317098a8c0cc745bbd4c94b9ed02401774cb0df9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197616"
---
# <a name="initializing-the-dialog-box"></a>初始化对话框

对话框及其所有控件创建完毕之后，在对话框中 ("类型") 出现在屏幕上时，将调用对话框对象的 [OnInitDialog](reference/cdialog-class.md#oninitdialog) 成员函数。 对于模式对话框，这种情况在 `DoModal` 调用期间出现。 对于无模式对话框， `OnInitDialog` 在调用时调用 `Create` 。 您通常可重写 `OnInitDialog` 来初始化对话框的控件，如设置编辑框的初始文本。 您必须从 `OnInitDialog` 的重写中调用基类 `CDialog` 的 `OnInitDialog` 成员函数。

如果要在应用程序) 中 (和所有其他对话框的背景颜色设置，请参阅 [设置对话框的背景色](setting-the-dialog-boxs-background-color.md)。

## <a name="see-also"></a>请参阅

[在 MFC 中使用对话框](life-cycle-of-a-dialog-box.md)
