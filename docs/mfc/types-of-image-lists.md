---
description: 了解详细信息：图像列表类型
title: 图像列表类型
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
ms.openlocfilehash: be18a523db366813a236fd4fd94bbb001345f0d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263733"
---
# <a name="types-of-image-lists"></a>图像列表类型

有两种类型的图像列表 ([CImageList](../mfc/reference/cimagelist-class.md)) ： draw 和掩码。 "Draw 图像列表" 由包含一个或多个图像的颜色位图组成。 "屏蔽的图像列表" 包含大小相等的两个位图。 第一种是包含图像的颜色位图，第二种是单色位图，其中包含一系列掩码-第一个位图中的每个图像一个。

成员函数的重载之一 `Create` 采用标志来指示图像列表是否被屏蔽。  ("其他重载" 创建屏蔽的图像列表。 ) 

绘制 draw 映像后，只需将其复制到目标设备上下文中;也就是说，它是在设备上下文的现有背景色上绘制的。 绘制屏蔽图像时，图像的位与掩码的位数组合在一起，这通常会在位图中生成透明区域，其中目标设备上下文的背景色通过显示。 绘制屏蔽图像时，可以指定多种绘制样式。 例如，可以指定图像进行抖动以指示所选对象。

## <a name="see-also"></a>请参阅

[使用 CImageList](../mfc/using-cimagelist.md)<br/>
[控件](../mfc/controls-mfc.md)
