---
description: 了解详细信息：如何：从 MFC 应用程序加载功能区资源
title: 如何：从 MFC 应用程序中加载功能区资源
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 231acbd475bf84b2623eb44f9a3500ab94145d06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330190"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>如何：从 MFC 应用程序中加载功能区资源

若要在应用程序中使用功能区资源，请修改应用程序以加载功能区资源。

### <a name="to-load-a-ribbon-resource"></a>加载功能区资源

1. 在 `Ribbon Control` 类中声明 `CMainFrame` 对象。

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. 在 `CMainFrame::OnCreate` 中，创建并初始化功能区控件。

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>请参阅

[功能区设计器 (MFC) ](ribbon-designer-mfc.md)
