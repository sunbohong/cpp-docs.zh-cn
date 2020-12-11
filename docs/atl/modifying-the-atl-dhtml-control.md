---
description: 了解详细信息：修改 ATL DHTML 控件
title: 修改 ATL DHTML 控件
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
ms.openlocfilehash: 7ae9c102addd7a33341a8f16105a3581de10481e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159448"
---
# <a name="modifying-the-atl-dhtml-control"></a>修改 ATL DHTML 控件

ATL 控件向导提供了起始代码，以便您可以生成和运行控件，因此您可以看到如何在项目文件中编写方法，以及如何使用调度方法在控件的 c + + 代码中调用这些方法。 可以将任何调度方法添加到接口。 然后，可以调用 HTML 资源中的方法。

## <a name="to-modify-the-atl-dhtml-control"></a>修改 ATL DHTML 控件

1. 在 **类视图** 中，展开控件项目。

   请注意，以 "UI" 结尾的接口有一种方法 `OnClick` 。 不以 "UI" 结尾的接口没有任何方法。

1. 添加一个名为的方法，该方法 `MethodInvoked` 不以 "UI" 结尾。

   此方法将添加到用于容器交互的控件容器中的接口，而不是添加到 DHTML 用于与控件交互的接口。 只有容器可以调用此方法。

1. 在 .cpp 文件中查找用作存根方法，并添加代码以显示消息框，例如：

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

1. 添加另一个名 `HelloHTML` 为的方法，只是将其添加到以 "UI" 结尾的接口。 `HelloHTML`在 .cpp 文件中查找用作存根方法，并添加代码以显示消息框，例如：

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

1. 将第三个方法添加 `GoToURL` 到不以 "UI" 结尾的接口。 通过调用 [IWebBrowser2：：导航](/previous-versions//aa752133\(v=vs.85\))实现此方法，如下所示：

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   你可以使用 `IWebBrowser2` 方法，因为 ATL 在 .h 文件中提供了指向该接口的指针。

接下来，修改 HTML 资源以调用你创建的方法。 您将添加三个按钮用于调用这些方法。

## <a name="to-modify-the-html-resource"></a>修改 HTML 资源

1. 在 **解决方案资源管理器** 中，双击 .htm 文件以显示 HTML 资源。

   检查 HTML，尤其是对外部 Windows 调度方法的调用。 HTML 调用项目的 `OnClick` 方法，参数指示控件的正文 (`theBody`) 和 ( "" ) 分配的颜色 `red` 。 方法调用后的文本是按钮上显示的标签。

1. 添加另一 `OnClick` 种方法，只更改颜色。 例如：

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   此方法将创建一个标记为 " **刷新**" 的按钮，用户可以单击该按钮将控件返回到原始的白色背景。

1. 添加对 `HelloHTML` 所创建的方法的调用。 例如：

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>
    ```

   此方法将创建一个标记为 " **HelloHTML**" 的按钮，用户可以单击该按钮以显示 `HelloHTML` 消息框。

现在，可以生成并 [测试修改后的 DHTML 控件](../atl/testing-the-modified-atl-dhtml-control.md)。

## <a name="see-also"></a>请参阅

[支持 DHTML 控件](../atl/atl-support-for-dhtml-controls.md)
