---
description: 了解详细信息：关闭 "可见时激活" 选项
title: 关闭“可见时激活”选项
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: fcb5f7ef0518cbf257ef9ee7a659c9617092b7d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263863"
---
# <a name="turning-off-the-activate-when-visible-option"></a>关闭“可见时激活”选项

控件具有两种基本状态：活动和非活动。 传统上，这些状态是由控件是否有窗口来区分。 活动控件具有窗口;不活动的控件没有。 引入无窗口激活后，这种区别不再是通用的，但仍适用于许多控件。

与通常由 ActiveX 控件执行的初始化的其余工作相比，创建窗口是一个资源消耗很大的操作。 理想情况下，控件会推迟创建其窗口，直到非要执行此操作。

许多控件在其在容器中可见的整个时间不需要是活动的。 通常，控件可保持不活动状态，直到用户执行需要此控件变为活动状态的操作（例如，使用鼠标单击或按 Tab 键）。 若要使控件在容器需要激活之前保持不活动状态，请从控件的杂项标志中删除 **OLEMISC_ACTIVATEWHENVISIBLE** 标志：

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

如果在创建控件时在 MFC ActiveX 控件向导的 "[控件设置](../mfc/reference/control-settings-mfc-activex-control-wizard.md)" 页中关闭 "**可见时激活**" 选项，则会自动省略 **OLEMISC_ACTIVATEWHENVISIBLE** 标志。

## <a name="see-also"></a>请参阅

[MFC ActiveX 控件：优化](../mfc/mfc-activex-controls-optimization.md)
