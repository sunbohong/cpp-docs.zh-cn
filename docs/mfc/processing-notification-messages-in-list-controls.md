---
description: 了解详细信息：处理列表控件中的通知消息
title: 处理列表控件中的通知消息
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: b761f5213a73ce31484a7a252b9b441da2fe154d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154794"
---
# <a name="processing-notification-messages-in-list-controls"></a>处理列表控件中的通知消息

当用户单击 "列标题"、"编辑标签" 等操作时，列表控件 ([CListCtrl](../mfc/reference/clistctrl-class.md)) 将通知消息发送到其父窗口。 如果您要在响应中做些什么，请处理这些消息。 例如，当用户单击列标题时，您可能要根据单击的列内容对项进行排序，与在 Microsoft Outlook 中一样。

从视图或对话框类的列表控件中处理 WM_NOTIFY 消息。 使用 [类向导](reference/mfc-class-wizard.md) 创建 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) 处理程序函数，其中包含基于正在处理的通知消息的 switch 语句。

有关列表控件可发送到其父窗口的通知的列表，请参阅 Windows SDK 中的 [列表视图控制引用](/windows/win32/Controls/list-view-control-reference) 。

## <a name="see-also"></a>请参阅

[使用 CListCtrl](../mfc/using-clistctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
