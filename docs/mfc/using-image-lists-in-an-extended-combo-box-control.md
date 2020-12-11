---
description: 了解详细信息：在扩展组合框控件中使用图像列表
title: 在扩展组合框控件中使用图像列表
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 9fb4b70f91a8ffc3d0175ec855cd005de10da280
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154365"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>在扩展组合框控件中使用图像列表

扩展组合框控件的主要功能是能够将图像列表中的图像与组合框控件中的单个项关联起来。 每一项都能够显示三个不同的图像：一个用于选定状态，一个用于 nonselected 状态，另一个用于覆盖图像。

下面的过程将图像列表与扩展组合框控件关联：

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>将图像列表与扩展组合框控件关联

1. 构造新的图像列表 (或使用现有图像列表对象) ，使用 [CImageList](../mfc/reference/cimagelist-class.md) 构造函数并存储结果指针。

1. 调用 [CImageList：： Create](../mfc/reference/cimagelist-class.md#create)来初始化新的 image list 对象。 下面的代码是此调用的一个示例。

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. 为每种可能的状态添加可选图像：选定或 nonselected，以及覆盖。 下面的代码添加三个预定义映像。

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. 使用对 [CComboBoxEx：： SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist)的调用将图像列表与控件相关联。

图像列表与控件相关联后，您可以单独指定每个项将用于三种可能状态的图像。 有关详细信息，请参阅 [设置单个项的图像](../mfc/setting-the-images-for-an-individual-item.md)。

## <a name="see-also"></a>请参阅

[使用 CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[控件](../mfc/controls-mfc.md)
