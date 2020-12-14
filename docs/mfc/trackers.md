---
description: 了解详细信息：跟踪器
title: 跟踪器
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
ms.openlocfilehash: e82766ecfabf2b5ebb0147b9f2c462f3b4460869
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264241"
---
# <a name="trackers"></a>跟踪器

[CRectTracker](../mfc/reference/crecttracker-class.md)类提供各种显示样式，在应用程序中的矩形项与用户之间提供用户界面。 这些样式包括实线、阴影线或虚线边框;覆盖项的阴影模式;和调整大小控点，可以位于边框的外部或内部。 跟踪器通常与 OLE 项结合使用，即从派生的对象 `COleClientItem` 。 跟踪器矩形在项的当前状态上显示视觉提示。

MFC OLE 示例 [OCLIENT](../overview/visual-cpp-samples.md) 演示了一个使用跟踪器和 OLE 客户端项的容器应用程序的通用接口。 有关跟踪器对象的不同样式和功能的演示，请参阅 MFC 常规示例 [跟踪](../overview/visual-cpp-samples.md)器。

有关在 OLE 应用程序中实现跟踪器的详细信息，请参阅[跟踪器：在 Ole 应用程序中实现跟踪](../mfc/trackers-implementing-trackers-in-your-ole-application.md)器

## <a name="see-also"></a>请参阅

[OLE](../mfc/ole-in-mfc.md)<br/>
[COleClientItem 类](../mfc/reference/coleclientitem-class.md)
