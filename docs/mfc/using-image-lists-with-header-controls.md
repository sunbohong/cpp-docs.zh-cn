---
description: 了解详细信息：使用带有标题控件的图像列表
title: 对标题控件使用图像列表
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 549f54c9fae7e0e0a63c726f4b75d2adeb38eef8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322726"
---
# <a name="using-image-lists-with-header-controls"></a>对标题控件使用图像列表

标头项能够显示标头项中的图像。 此图像存储在关联的图像列表中，为 16 x 16 像素，与列表视图控件中使用的图标图像具有相同的特征。 为了成功实现此行为，您必须首先创建并初始化图像列表，将列表与标题控件关联，然后修改将显示图像的标头项的特性。

下面的过程演示了详细信息，使用指向标题控件的指针 (`m_pHdrCtrl`) ，并 () 指向图像列表的指针 `m_pHdrImages` 。

### <a name="to-display-an-image-in-a-header-item"></a>显示标头项中的图像

1. 构造新的图像列表 (或使用现有的图像列表对象) 使用 [CImageList](../mfc/reference/cimagelist-class.md) 构造函数存储结果指针。

1. 调用 [CImageList：： Create](../mfc/reference/cimagelist-class.md#create)来初始化新的 image list 对象。 下面的代码是此调用的一个示例。

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. 为每个标头项添加映像。 下面的代码添加了两个预定义的映像。

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. 使用对 [CHeaderCtrl：： SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)的调用将图像列表与标头控件相关联。

1. 修改标题项以显示关联的图像列表中的图像。 下面的示例将第一个图像（从 `m_phdrImages` ）分配给第一个标头项 `m_pHdrCtrl` 。

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

有关所用参数值的详细信息，请参阅相关 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)。

> [!NOTE]
> 使用同一个图像列表可以具有多个控件。 例如，在标准列表视图控件中，列表视图控件的小图标视图和列表视图控件的标题项都可以使用图像列表 (16 x 16 像素的图像) 。

## <a name="see-also"></a>请参阅

[使用 CHeaderCtrl](../mfc/using-cheaderctrl.md)
