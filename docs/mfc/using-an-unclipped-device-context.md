---
description: 了解详细信息：使用未剪辑设备上下文
title: 使用未剪辑的设备上下文
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 76131d35b108b04caf0b07be8c46e250120f9f62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202634"
---
# <a name="using-an-unclipped-device-context"></a>使用未剪辑的设备上下文

如果您完全确定您的控件不会在其客户端矩形的外部进行绘制，则可以通过禁用对由 `IntersectClipRect` 创建的 `COleControl` 的调用来实现较小但可检测到的增速。 为此，请从 [COleControl：： GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)返回的一组标志中删除 *clipPaintDC* 标志。 例如：

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

如果你在 "[控件设置](../mfc/reference/control-settings-mfc-activex-control-wizard.md)" 页上选择了 "**未剪辑设备上下文**" 选项，则在通过 MFC ActiveX 控件向导创建控件时，将自动生成删除此标志的代码。

如果使用无窗口激活，则此优化不起作用。

## <a name="see-also"></a>请参阅

[MFC ActiveX 控件：优化](../mfc/mfc-activex-controls-optimization.md)
