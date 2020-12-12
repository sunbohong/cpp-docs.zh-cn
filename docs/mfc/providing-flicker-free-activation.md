---
description: 了解详细信息：提供 Flicker-Free 激活
title: 提供无闪烁激活
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
ms.openlocfilehash: c0af1ccdd4795f55296ff38e0e74bc6492f79eb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248822"
---
# <a name="providing-flicker-free-activation"></a>提供无闪烁激活

如果控件在非活动 (状态和活动状态下都以相同的方式绘制，并且不使用无窗口激活) ，则可以消除绘图操作和伴随的视觉闪烁，这种情况通常会在非活动状态和活动状态之间进行转换时出现。 为此，请在 [COleControl：： GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)返回的一组标志中包含 **noFlickerActivate** 标志。 例如：

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

如果在通过 MFC ActiveX 控件向导创建控件时在 "[控件设置](../mfc/reference/control-settings-mfc-activex-control-wizard.md)" 页上选择 "**无闪烁激活**" 选项，则会自动生成包含此标志的代码。

如果使用无窗口激活，则此优化不起作用。

## <a name="see-also"></a>请参阅

[MFC ActiveX 控件：优化](../mfc/mfc-activex-controls-optimization.md)
