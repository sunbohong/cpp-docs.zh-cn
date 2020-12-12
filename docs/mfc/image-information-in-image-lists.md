---
description: 了解详细信息：图像列表中的图像信息
title: 图像列表中的图像信息
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: c3a5f1cee0a06177d12b72673bf0ebf8e1a73933
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290136"
---
# <a name="image-information-in-image-lists"></a>图像列表中的图像信息

[CImageList](reference/cimagelist-class.md) 包括多个从图像列表中检索信息的函数。 [GetImageInfo](reference/cimagelist-class.md#getimageinfo)成员函数 `IMAGEINFO` 使用有关单个图像的信息填充结构，其中包括图像和掩码位图的句柄、颜色平面数和每个像素的位数以及图像位图中图像的边框。 您可使用此信息直接操作图像的位图。

[GetImageCount](reference/cimagelist-class.md#getimagecount)成员函数检索图像列表中的图像数量。

您可以使用 [ExtractIcon](reference/cimagelist-class.md#extracticon) 成员函数基于图像列表中的图像和掩码创建图标。 此函数将返回新图标的句柄。

## <a name="see-also"></a>请参阅

[使用 CImageList](using-cimagelist.md)<br/>
[控件](controls-mfc.md)
