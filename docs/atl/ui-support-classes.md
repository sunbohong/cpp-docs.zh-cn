---
description: 了解详细信息： UI 支持类
title: 'UI 支持类 (ATL) '
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
ms.openlocfilehash: d8bc345db05ef886c2a054356ae6bd8d299c8045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138250"
---
# <a name="ui-support-classes"></a>UI 支持类

以下类提供一般的 UI 支持：

- [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) Microsoft HTML 分析和呈现引擎的接口。

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) 提供容器与控件进行通信时使用的主要方法。 管理就地控件的激活和停用。

- [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) 管理就地控件的重新激活。 允许无窗口控件接收消息，以及参与拖放操作。

- [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) 协助就地控件与其容器之间的通信。

- [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md) 使控件能够直接显示自身，并通知容器的显示更改。 提供对无闪烁绘图、非矩形和透明控件的支持，并进行命中测试。

## <a name="related-articles"></a>相关文章

[ATL 教程](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)
