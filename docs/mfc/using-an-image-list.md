---
description: 了解详细信息：使用图像列表
title: 使用图像列表
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 92587bd80a4f613a04cae22322ab258e9869d247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202686"
---
# <a name="using-an-image-list"></a>使用图像列表

图像列表的典型用法遵循下面的模式：

- 构造一个 [CImageList](../mfc/reference/cimagelist-class.md) 对象，并调用其 [Create](../mfc/reference/cimagelist-class.md#create) 函数的重载之一来创建一个图像列表，并将其附加到 `CImageList` 对象。

- 如果在创建图像列表时未添加图像，请通过调用 [add](../mfc/reference/cimagelist-class.md#add) 或 [Read](../mfc/reference/cimagelist-class.md#read) 成员函数向图像列表添加图像。

- 通过调用该控件的相应成员函数将图像列表与控件相关联，或使用图像列表的 [绘制](../mfc/reference/cimagelist-class.md#draw) 成员函数自行从图像列表中绘制图像。

- 也许允许用户使用 "拖动" 图像列表的内置支持来拖动图像。

> [!NOTE]
> 如果图像列表是用运算符创建的 **`new`** ，则必须在完成后销毁 `CImageList` 对象。

## <a name="see-also"></a>请参阅

[使用 CImageList](../mfc/using-cimagelist.md)<br/>
[控件](../mfc/controls-mfc.md)
