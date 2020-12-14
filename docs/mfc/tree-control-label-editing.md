---
description: 了解详细信息：树控件标签编辑
title: 树控件标签编辑
ms.date: 11/04/2016
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
ms.openlocfilehash: b471b2ce9773ec86b1e4f94e766d3428fef456fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264006"
---
# <a name="tree-control-label-editing"></a>树控件标签编辑

用户可以直接编辑树控件中项的标签 (具有 **TVS_EDITLABELS** 样式的 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 。 用户通过单击具有焦点的项的标签开始编辑。 应用程序开始使用 [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) 成员函数进行编辑。 树控件在编辑开始以及编辑取消或完成时发送通知。 当编辑完成时，您负责根据需要更新项的标签。

开始编辑标签时，树控件将发送 [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) 通知消息。 通过处理此通知，您可以允许某些标签的编辑并阻止其他标签的编辑。 返回 0 将允许编辑，返回非零将阻止编辑。

当标签编辑已取消或已完成时，树控件将发送 [TVN_ENDLABELEDIT](/windows/win32/Controls/tvn-endlabeledit) 通知消息。 *LParam* 参数是 [NMTVDISPINFO](/windows/win32/api/commctrl/ns-commctrl-nmtvdispinfow)结构的地址。 **项** 成员是标识项并包含已编辑的文本的 [TVITEM](/windows/win32/api/commctrl/ns-commctrl-tvitemw)结构。 您负责根据需要更新项的标签（可能在验证编辑过的字符串之后）。 如果取消编辑，则的 *pszText* 成员 `TV_ITEM` 为0。

在编辑标签时，通常是为了响应 [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) 通知消息，您可以使用 [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) 成员函数获取指向用于标签编辑的编辑控件的指针。 您可以调用编辑控件的 [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) 成员函数，以限制用户可输入的文本量或用于截获和丢弃无效字符的编辑控件的子类。 但请注意，只有在发送 **TVN_BEGINLABELEDIT** *之后*，才会显示编辑控件。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)
