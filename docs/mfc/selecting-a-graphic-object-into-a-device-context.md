---
description: 了解详细信息：在设备上下文中选择图形对象
title: 将图形对象选入设备上下文
ms.date: 11/04/2016
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
ms.openlocfilehash: cc2aabbcb1614fc77e5eadf9e6fba13ba377a4c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217674"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>将图形对象选入设备上下文

本主题适用于在窗口的设备上下文中使用图形对象的情况。 [创建图形对象](../mfc/one-stage-and-two-stage-construction-of-objects.md)之后，必须将其选择到设备上下文中，而不是存储在该对象中的默认对象：

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>图形对象的生存期

[SelectObject](../mfc/reference/cdc-class.md#selectobject)返回的图形对象为 "临时"。 也就是说，它将[](../mfc/reference/cwinapp-class.md#onidle) `CWinApp` 在下一次程序获取空闲时间时由类的 OnIdle 成员函数删除。 只要在单个函数中使用返回的对象 `SelectObject` ，而不向主消息循环返回控制权，就不会有任何问题。

### <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [图形对象](../mfc/graphic-objects.md)

- [图形对象的一阶段和两阶段构造](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [设备上下文](../mfc/device-contexts.md)

- [在视图中绘制](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>请参阅

[图形对象](../mfc/graphic-objects.md)
