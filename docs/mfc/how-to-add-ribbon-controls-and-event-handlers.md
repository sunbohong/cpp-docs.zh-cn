---
description: 了解详细信息：如何：添加功能区控件和事件处理程序
title: 如何：添加功能区控件和事件处理程序
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: bffac6b27f809961e3ca7a4323f519c765526198
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290292"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>如何：添加功能区控件和事件处理程序

功能区控件是添加到面板的元素，如按钮和组合框。 面板是显示一组相关控件的功能区栏区域。

在本主题中，你将打开功能区设计器，添加一个按钮，然后链接显示 "Hello World" 的事件。

### <a name="to-open-the-ribbon-designer"></a>打开功能区设计器

1. 在 Visual Studio 的 " **视图** " 菜单上，单击 " **资源视图**"。

1. 在 **资源视图** 中，双击功能区资源以在设计图面上显示它。

### <a name="to-add-a-button-and-an-event-handler"></a>添加按钮和事件处理程序

1. 从 **工具栏** 中，单击 " **按钮** "，然后将其拖到设计图面中的一个面板上。

1. 右键单击该按钮，然后单击 " **添加事件处理程序**"。

1. 在 **事件处理程序向导** 中，确认默认设置，然后单击 " **添加" 和 "编辑**"。 有关详细信息，请参阅 [事件处理程序向导](../ide/adding-an-event-handler-visual-cpp.md#event-handler-wizard)。

1. 在代码编辑器中，将以下代码添加到处理程序函数：

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>请参阅

[RibbonGadgets 示例：功能区小工具应用程序](../overview/visual-cpp-samples.md)<br/>
[功能区设计器 (MFC) ](ribbon-designer-mfc.md)
