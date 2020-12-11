---
description: '了解详细信息：将控件置于网页上 (ATL 教程，第7部分) '
title: 将控件置于网页上（ATL 教程，第 7 部分）
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
ms.openlocfilehash: 738d847a6436a2afab2e336502ec3255d1a1e589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159174"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>将控件置于网页上（ATL 教程，第 7 部分）

控件现在已完成。 若要在实际情况下查看控件，请将其放在网页上。 定义控件时创建了包含控件的 HTML 文件。 从 **解决方案资源管理器** 打开 PolyCtl.htm 文件，您可以在网页上看到您的控件。

在此步骤中，您将向控件添加功能并为网页编写脚本以响应事件。 您还将修改控件，使 Internet Explorer 知道控件对于脚本编写是安全的。

## <a name="adding-new-functionality"></a>添加新功能

### <a name="to-add-control-features"></a>添加控件功能

1. 打开 Polyctl.htm 并替换以下代码：

    ```cpp
    if (PtInRegion(hRgn, xPos, yPos))
        Fire_ClickIn(xPos, yPos);
    else
        Fire_ClickOut(xPos, yPos);
    ```

    替换为

    ```cpp
    short temp = m_nSides;
    if (PtInRegion(hRgn, xPos, yPos))
    {
        Fire_ClickIn(xPos, yPos);
        put_Sides(++temp);
    }
    else
    {
        Fire_ClickOut(xPos, yPos);
        put_Sides(--temp);
    }
    ```

该形状现在将根据您单击的位置添加或删除边缘。

## <a name="scripting-the-web-page"></a>编写网页脚本

控件尚未执行任何操作，因此请更改网页以响应您发送的事件。

### <a name="to-script-the-web-page"></a>编写网页脚本

1. 打开 PolyCtl.htm，然后选择 "HTML 视图"。 向 HTML 代码添加以下行。 应在之后但在 `</OBJECT>` 之前添加它们 `</BODY>` 。

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - adding side")
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - removing side")
        End Sub
    -->
    </SCRIPT>
    ```

1. 保存 HTM 文件。

你已添加了一些 VBScript 代码，用于从控件获取端属性。 如果在控件内部单击，则会将边数增加1。 如果在控件外单击，则可以将边数减少一。

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>指示控件对于脚本编写是安全的

只能在 Internet Explorer 中查看具有控件的网页。 由于存在安全漏洞，其他浏览器不再支持 ActiveX 控件。

> [!NOTE]
> 如果该控件不可见，则知道某些浏览器需要设置调整才能运行 ActiveX 控件。 请参阅浏览器文档，了解如何启用 ActiveX 控件。

根据当前的 Internet Explorer 安全设置，可能会出现 "安全警报" 对话框。 这表明控件在脚本上可能不安全，并且可能会损坏。 例如，如果您有一个显示文件的控件，但有一个 `Delete` 删除文件的方法，则如果您刚刚在页面上查看该控件，则该控件是安全的。 但脚本可能不安全，因为有人可以调用 `Delete` 方法。

> [!IMPORTANT]
> 在本教程中，可以更改 Internet Explorer 中的安全设置，以运行未标记为安全的 ActiveX 控件。 在控制面板中，单击 " **Internet 属性** "，然后单击 " **安全** " 以更改适当的设置。 完成本教程后，请将安全设置更改回其原始状态。

您可以通过编程方式提醒 Internet Explorer 无需显示此特定控件的 "安全警报" 对话框。 可以使用接口执行此操作 `IObjectSafety` 。 ATL 在类 [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md)中提供此接口的实现。 若要将接口添加到控件，请将添加 `IObjectSafetyImpl` 到继承类的列表中，并在 COM 映射中为其添加一个项。

### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>将 IObjectSafetyImpl 添加到控件

1. 将以下行添加到 Polyctl.htm 中的继承类列表的末尾，并在上一行中添加一个逗号：

    [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

1. 将以下行添加到 Polyctl.htm 中的 COM 映射：

    [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>生成和测试控件

生成控件。 完成生成后，再次在浏览器视图中打开 PolyCtl.htm。 此时，应直接显示网页，而不显示 " **安全警报** " 对话框。 如果在多边形内单击，则边数将增加1。 单击多边形的外部可减少边数。

[返回到步骤6](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>后续步骤

本步骤将结束 ATL 教程。 有关 ATL 的详细信息的链接，请参阅 [atl 起始页](../atl/active-template-library-atl-concepts.md)。

## <a name="see-also"></a>请参阅

[教程](../atl/active-template-library-atl-tutorial.md)
