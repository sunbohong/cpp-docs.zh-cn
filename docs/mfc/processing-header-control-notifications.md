---
description: 了解详细信息：处理 Header-Control 通知
title: 处理标题控件通知
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: ac1cdbf5efc3e82cdf417a38072cf344ca2ee1a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154846"
---
# <a name="processing-header-control-notifications"></a>处理标题控件通知

在视图或对话框类中，使用 [类向导](reference/mfc-class-wizard.md) 创建 [OnChildNotify](reference/cwnd-class.md#onchildnotify) 处理程序函数，该函数具有用于任何标头控件 ([CHeaderCtrl](reference/cheaderctrl-class.md)) 通知消息的 Switch 语句， (参阅将 [消息映射到函数](reference/mapping-messages-to-functions.md)) 。 当用户单击或双击标题项、拖动项之间的分隔符，等等时，通知将发送到父窗口。

Windows SDK 中的 [标头控件引用](/windows/win32/controls/header-control-reference) 中列出了与标头控件关联的通知消息。

## <a name="see-also"></a>请参阅

[使用 CHeaderCtrl](using-cheaderctrl.md)<br/>
[控件](controls-mfc.md)
