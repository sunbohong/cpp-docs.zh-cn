---
description: 了解详细信息：可视化管理器
title: 可视化管理器
ms.date: 11/19/2018
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
ms.openlocfilehash: b99331503e4e7e69cc5d8a19fde7641c1b1daeeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143203"
---
# <a name="visualization-manager"></a>可视化管理器

可视化管理器是一个控制整个应用程序外观的对象。 它充当单个类，您可以在其中放置应用程序的所有绘制代码。 MFC 库包含多个可视化管理器。 如果要为应用程序创建自定义视图，还可以创建自己的可视化管理器。 以下图像显示启用了不同视觉对象管理器的同一应用程序：

![由 CMFCVisualManagerWindows 呈现的 MyApp](../mfc/media/vmwindows.png "由 CMFCVisualManagerWindows 呈现的 MyApp") <br/>
使用 CMFCVisualManagerWindows 视觉对象管理器的 MyApp

![由 CMFCVisualManagerVS2005 呈现的 MyApp](../mfc/media/vmvs2005.png "由 CMFCVisualManagerVS2005 呈现的 MyApp") <br/>
使用 CMFCVisualManagerVS2005 视觉对象管理器的 MyApp

![由 CMFCVisualManagerOfficeXP 呈现的 MyApp](../mfc/media/vmofficexp.png "由 CMFCVisualManagerOfficeXP 呈现的 MyApp") <br/>
使用 CMFCVisualManagerOfficeXP 视觉对象管理器的 MyApp

![由 CMFCVisualManagerOffice2003 呈现的 MyApp](../mfc/media/vmoffice2003.png "由 CMFCVisualManagerOffice2003 呈现的 MyApp") <br/>
使用 CMFCVisualManagerOffice2003 视觉对象管理器的 MyApp

![由 CMFCVisualManagerOffice2007 呈现的 MyApp](../mfc/media/msoffice2007.png "由 CMFCVisualManagerOffice2007 呈现的 MyApp") <br/>
使用 CMFCVisualManagerOffice2007 视觉对象管理器的 MyApp

默认情况下，可视化管理器将为多个 GUI 元素维护绘图代码。 若要提供自定义 UI 元素，需要重写可视管理器的相关绘图方法。 有关这些方法的列表，请参阅 [CMFCVisualManager 类](../mfc/reference/cmfcvisualmanager-class.md)。 可以重写以提供自定义外观的方法是以开头的所有方法 `OnDraw` 。

应用程序只能有一个 `CMFCVisualManager` 对象。 若要获取指向应用程序的可视化管理器的指针，请调用静态函数 [CMFCVisualManager：： GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance)。 由于所有可视化管理器都继承自 `CMFCVisualManager` ，因此该 `CMFCVisualManager::GetInstance` 方法将获得指向相应可视管理器的指针，即使您创建了一个自定义视觉对象管理器也是如此。

如果你想要创建自定义的视觉对象管理器，你必须从已存在的可视管理器中派生它。 派生自的默认类是 `CMFCVisualManager` 。 但是，如果它更适合应用程序的所需内容，则可以使用不同的可视化管理器。 例如，如果你想要使用 `CMFCVisualManagerOffice2007` 可视化管理器，但只想更改分隔符的外观，则可以从派生自定义类 `CMFCVisualManagerOffice2007` 。 在这种情况下，应仅覆盖用于绘制分隔符的方法。

可以通过两种方式将特定的可视化管理器用于应用程序。 一种方法是调用 [CMFCVisualManager：： SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) 方法，并以参数的形式传递适当的可视化管理器。 下面的代码示例演示如何 `CMFCVisualManagerVS2005` 通过此方法使用视觉对象管理器：

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

在应用程序中使用可视化管理器的另一种方法是手动创建。 然后，应用程序会将此新的视觉管理器用于所有呈现。 但是，因为 `CMFCVisualManager` 每个应用程序只能有一个对象，所以在创建新的可视化管理器之前，必须先删除当前的可视化管理器。 在下面的示例中， `CMyVisualManager` 是派生自的自定义可视化管理器 `CMFCVisualManager` 。 以下方法将根据索引更改用于显示应用程序的视觉对象管理器：

```cpp
void CMyApp::SetSkin (int index)
{
    if (CMFCVisualManager::GetInstance() != NULL)
    {
        delete CMFCVisualManager::GetInstance();
    }

    switch (index)
    {
    case DEFAULT_STYLE:
        // The following statement creates a new CMFCVisualManager
        CMFCVisualManager::GetInstance();
        break;

    case CUSTOM_STYLE:
        new CMyVisualManager;
        break;

    default:
        CMFCVisualManager::GetInstance();
        break;
    }

    CMFCVisualManager::GetInstance()->RedrawAll();
}
```

## <a name="see-also"></a>请参阅

[用户界面元素](../mfc/user-interface-elements-mfc.md)<br/>
[CMFCVisualManager 类](../mfc/reference/cmfcvisualmanager-class.md)
