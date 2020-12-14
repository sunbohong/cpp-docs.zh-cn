---
description: 了解详细信息：树控件通知消息
title: 树控件通知消息
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: 899b6469a2de9a076dd33e62c5023f502448d45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263980"
---
# <a name="tree-control-notification-messages"></a>树控件通知消息

 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 的树控件作为 WM_NOTIFY 消息发送以下通知消息：

|通知消息|描述|
|--------------------------|-----------------|
|TVN_BEGINDRAG|发出拖放操作开始信号|
|TVN_BEGINLABELEDIT|指示就地标签编辑开始|
|TVN_BEGINRDRAG|使用鼠标右键指示开始拖放操作的开始|
|TVN_DELETEITEM|指示删除特定项|
|TVN_ENDLABELEDIT|发出标签编辑结束信号|
|TVN_GETDISPINFO|请求树控件显示项所需的信息|
|TVN_ITEMEXPANDED|指示已展开或折叠父项的子项列表|
|TVN_ITEMEXPANDING|通知要展开或折叠父项的子项列表|
|TVN_KEYDOWN|通知键盘事件|
|TVN_SELCHANGED|指示所选内容已从一项更改为另一项|
|TVN_SELCHANGING|指示所选内容将从一项更改为另一项|
|TVN_SETDISPINFO|用于更新为某项维护的信息的通知|

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)
