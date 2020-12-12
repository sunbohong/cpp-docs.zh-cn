---
description: 了解详细信息： ATL COM 属性页
title: ATL COM 属性页
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
ms.openlocfilehash: 252e8a98f4f34a07a374c77fc48aacd7eee8969f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165974"
---
# <a name="atl-com-property-pages"></a>ATL COM 属性页

COM 属性页提供了一个用户界面，用于设置 (或调用一个或多个 COM 对象) 的方法的属性。 ActiveX 控件广泛地使用属性页，提供丰富的用户界面，使用户能够在设计时设置控件属性。

属性页是实现 [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) 或 [IPROPERTYPAGE2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) 接口的 COM 对象。 这些接口提供了一些方法，这些方法允许页面与 `site` (表示页面容器的 com 对象) 和多个 *对象* (com 对象，这些对象将调用其方法以响应属性页) 的用户所做的更改。 属性页容器负责在属性页接口上调用方法，以通知页面何时显示或隐藏其用户界面，以及何时将用户所做的更改应用于基础对象。

每个属性页可以完全独立于可设置其属性的对象生成。 属性页需要了解 (或一组接口) 的特定接口，并提供用于在该接口上调用方法的用户界面。

有关详细信息，请参阅 Windows SDK 中的 [属性表和属性页](/windows/win32/com/property-sheets-and-property-pages) 。

## <a name="in-this-section"></a>本节内容

[指定属性页](../atl/specifying-property-pages.md)<br/>
列出指定控件的属性页并显示示例类的步骤。

[实现属性页](../atl/implementing-property-pages.md)<br/>
列出实现属性页的步骤，包括要重写的方法。 指导您完成基于 ATLPages 示例程序的完整示例。

## <a name="related-sections"></a>相关章节

[ATLPages 示例](../overview/visual-cpp-samples.md)<br/>
ATLPages 示例的示例抽象，使用实现属性页 `IPropertyPageImpl` 。

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
提供了关于如何使用 Active Template Library 进行编程的概念性主题的链接。

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)
