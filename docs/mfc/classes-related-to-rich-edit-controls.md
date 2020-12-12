---
description: 了解更多：与 Rich Edit 控件相关的类
title: 与 Rich Edit 控件相关的类
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], and CRichEditItem
- CRichEditCtrl class [MFC], related classes
- CRichEditDoc class [MFC], Rich Edit controls
- rich edit controls [MFC], classes related to
- classes [MFC], related to rich edit controls
- rich edit controls [MFC], and CRichEditView
- CRichEditCtrlItem class and CRichEditCtrl
- rich edit controls [MFC], and CRichEditDoc
- CRichEditView class [MFC], and CRichEditCtrl
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
ms.openlocfilehash: b44c5a874c7f48c132f31483bf5ee73eafbe4da5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176673"
---
# <a name="classes-related-to-rich-edit-controls"></a>与 Rich Edit 控件相关的类

[CRichEditView](reference/cricheditview-class.md)、 [CRichEditDoc](reference/cricheditdoc-class.md)和[CRichEditCntrItem](reference/cricheditcntritem-class.md)类提供了) 在 MFC 文档/视图体系结构上下文中 ([CRichEditCtrl](reference/cricheditctrl-class.md)的丰富编辑控件功能。 `CRichEditView` 保留文本及其格式特征。 `CRichEditDoc` 保留视图中的 OLE 客户端项的列表。 `CRichEditCntrItem` 提供对 OLE 客户端项的容器端访问。 若要修改的内容 `CRichEditView` ，请使用 [CRichEditView：： GetRichEditCtrl](reference/cricheditview-class.md#getricheditctrl) 访问基础丰富编辑控件。

## <a name="see-also"></a>请参阅

[使用 CRichEditCtrl](using-cricheditctrl.md)<br/>
[控件](controls-mfc.md)
