---
title: 模式和无模式对话框
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: d3497a19ab14dcc9f14dc0419eb65ea033135b6e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508856"
---
# <a name="modal-and-modeless-dialog-boxes"></a>模式和无模式对话框

可以使用类 [CDialog](reference/cdialog-class.md) 来管理两种类型的对话框：

- *模式对话框*，要求用户在继续之前做出响应

- *无模式对话框*，可随时停留在屏幕上，但允许其他用户活动使用

用于创建对话框模板的资源编辑和过程对于模式对话框和无模式对话框是相同的。

为程序创建对话框需要执行以下步骤：

1. 使用 [对话框编辑器](../windows/dialog-editor.md) 设计对话框，并创建其对话框模板资源。

1. 创建对话框类。

1. 将 [对话框资源的控件连接到](../windows/adding-editing-or-deleting-controls.md) 对话框类中的消息处理程序。

1. 添加与对话框控件关联的数据成员，并为控件指定 [对话框数据交换](dialog-data-exchange.md) 和 [对话框数据验证](dialog-data-validation.md) 。

## <a name="see-also"></a>请参阅

[对话框](dialog-boxes.md)<br/>
[在 MFC 中使用对话框](life-cycle-of-a-dialog-box.md)
