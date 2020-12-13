---
description: 了解详细信息：向标题控件添加项
title: 向标题控件添加项
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
ms.openlocfilehash: 91c33a7528f6637a91181559d71ed82b13420b38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339064"
---
# <a name="adding-items-to-the-header-control"></a>向标题控件添加项

创建标头控件之后 ([CHeaderCtrl](reference/cheaderctrl-class.md)) 在其父窗口中，根据需要添加任意数量的 "标头项"：通常每列一个。

### <a name="to-add-a-header-item"></a>添加标题项

1. 准备 [HD_ITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 结构。

1. 调用 [CHeaderCtrl：： InsertItem](reference/cheaderctrl-class.md#insertitem)，传递结构。

1. 对于其他项，重复步骤 1 和 2。

有关详细信息，请参阅在 Windows SDK 中 [向标题控件添加项](/windows/win32/Controls/header-controls) 。

## <a name="see-also"></a>请参阅

[使用 CHeaderCtrl](using-cheaderctrl.md)<br/>
[控件](controls-mfc.md)
