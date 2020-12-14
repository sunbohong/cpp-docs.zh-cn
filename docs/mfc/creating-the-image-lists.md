---
description: 了解详细信息：创建映像列表
title: 创建图像列表
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: f2776902e7be06161bdbcfad23bd21d9188467f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309662"
---
# <a name="creating-the-image-lists"></a>创建图像列表

无论你使用的是 [CListView](reference/clistview-class.md) 还是 [CListCtrl](reference/clistctrl-class.md)，创建图像列表都是相同的。

> [!NOTE]
> 如果列表控件包含样式，则仅需要图像列表 `LVS_ICON` 。

使用类 `CImageList` 创建一个或多个图像列表， () 的全尺寸图标、小图标和状态。 请参阅 [CImageList](reference/cimagelist-class.md)，然后查看 Windows SDK 中的 [列表视图图像列表](/windows/win32/Controls/using-list-view-controls) 。

为每个图像列表调用 [CListCtrl：： SetImageList](reference/clistctrl-class.md#setimagelist) ;将指针传递到适当的 `CImageList` 对象。

## <a name="see-also"></a>请参阅

[使用 CListCtrl](using-clistctrl.md)<br/>
[控件](controls-mfc.md)
