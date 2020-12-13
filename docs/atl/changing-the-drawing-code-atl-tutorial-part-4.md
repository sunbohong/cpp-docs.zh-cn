---
description: '了解更多相关信息：更改绘图代码 (ATL 教程，第4部分) '
title: 更改绘图代码（ATL 教程，第 4 部分）
ms.custom: get-started-article
ms.date: 09/26/2018
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
ms.openlocfilehash: 4d134930bf2c9bc886a3c59a68db5a52f7c6ca7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153377"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>更改绘图代码（ATL 教程，第 4 部分）

默认情况下，控件的绘制代码显示正方形和文本 **polyctl.htm**。 在此步骤中，你将更改代码以显示更有趣的内容。 涉及以下任务：

- 修改头文件

- 修改 `OnDraw` 函数

- 添加用于计算多边形点的方法

- 初始化填充颜色

## <a name="modifying-the-header-file"></a>修改头文件

首先添加对数学函数的支持， `sin` 并通过 `cos` 创建用于存储位置的数组来计算多边形点。

### <a name="to-modify-the-header-file"></a>修改头文件

1. 将行添加 `#include <math.h>` 到 polyctl.htm 顶部。 文件顶部应该如下所示：

    [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

1. `IProvideClassInfo`通过将以下代码添加到 polyctl.htm 来实现接口，以提供控件的方法信息。 在 `CPolyCtl` 类中，将 line 替换为：

    ```cpp
    public CComControl<CPolyCtl>
    ```

    替换为

    ```cpp
    public CComControl<CPolyCtl>,
    public IProvideClassInfo2Impl<&CLSID_PolyCtl, &DIID__IPolyCtlEvents, &LIBID_PolygonLib>
    ```

    在中 `BEGIN_COM_MAP(CPolyCtl)` ，添加以下行：

    ```cpp
    COM_INTERFACE_ENTRY(IProvideClassInfo)
    COM_INTERFACE_ENTRY(IProvideClassInfo2)
    ```

1. 计算多边形点后，它们将存储在类型的数组中 `POINT` ，因此 `short m_nSides;` 在 polyctl.htm 中的定义语句后添加数组：

    [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>修改 OnDraw 方法

现在应 `OnDraw` 在 polyctl.htm 中修改方法。 要添加的代码会创建一个新的笔和画笔，用于绘制多边形，然后调用 `Ellipse` 和 `Polygon` Win32 API 函数来执行实际绘图。

### <a name="to-modify-the-ondraw-function"></a>修改 OnDraw 函数

1. `OnDraw`将 polyctl.htm 中的现有方法替换为以下代码：

    [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>添加用于计算多边形点的方法

添加一个名为的方法， `CalcPoints` 该方法将计算构成多边形外围的点的坐标。 这些计算将基于传递到函数中的 RECT 变量。

### <a name="to-add-the-calcpoints-method"></a>添加 CalcPoints 方法

1. 将的声明添加 `CalcPoints` 到 `IPolyCtl` `CPolyCtl` polyctl.htm 中类的 public 节：

    [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

    类的 public 部分的最后一部分将如下所 `CPolyCtl` 示：

    [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

1. 将此函数的实现添加 `CalcPoints` 到 polyctl.htm 的末尾：

    [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>初始化填充颜色

`m_clrFillColor`使用默认颜色初始化。

### <a name="to-initialize-the-fill-color"></a>初始化填充颜色

1. 使用绿色作为默认颜色，方法是将以下行添加到 `CPolyCtl` polyctl.htm 中的构造函数：

    [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

构造函数现在如下所示：

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>生成和测试控件

重新生成控件。 如果 PolyCtl.htm 文件仍处于打开状态，请确保该文件处于关闭状态，然后单击 "**生成**" 菜单上的 "**生成多边形**"。 您可以再次从 PolyCtl.htm 页查看控件，但这次请使用 ActiveX 控件测试容器。

### <a name="to-use-the-activex-control-test-container"></a>使用 ActiveX 控件测试容器

1. 生成并启动 ActiveX 控件测试容器。 TSTCON 示例：可在 GitHub 上找到 [ActiveX 控件测试容器](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/ole/TstCon) 。

    > [!NOTE]
    > 对于涉及的错误， `ATL::CW2AEX` 在 Script 中，将 line 替换 `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT );` 为 `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT.m_psz );` ，并将 line 替换为 `TRACE( "Source Text: %s\n", COLE2CT( bstrSourceLineText ) );` `TRACE( "Source Text: %s\n", bstrSourceLineText );` 。<br/>
    > 对于涉及的错误 `HMONITOR` ，请在项目中打开 stdafx.h `TCProps` 并替换：
    >
    > ```cpp
    > #ifndef WINVER
    > #define WINVER 0x0400
    > #endif
    > ```
    >
    > 替换为
    >
    > ```cpp
    > #ifndef WINVER
    > #define WINVER 0x0500
    > #define _WIN32_WINNT 0x0500
    > #endif
    > ```

1. 在 **测试容器** 的 " **编辑** " 菜单上，单击 " **插入新控件**"。

1. 找到将调用的控件， `PolyCtl class` 然后单击 **"确定"**。 圆圈内会出现绿色三角形。

尝试按下一个过程更改边数。 若要从 **测试容器** 内修改双重接口的属性，请使用 **Invoke 方法**。

### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>从测试容器内修改控件的属性

1. 在 "**测试容器**" 中，单击 "**控制**" 菜单上的 "**调用方法**"。

    将显示 " **调用方法** " 对话框。

1. 从 "**方法名称**" 下拉列表框中选择 "**边**" 属性的 " **PropPut** " 版本。

1. `5`在 "**参数值**" 框中键入，单击 "**设置值**"，然后单击 "**调用**"。

请注意，控件不会更改。 尽管通过设置变量在内部更改了边数 `m_nSides` ，但这不会导致控件重绘。 如果切换到其他应用程序，然后再切换回 **测试容器**，则会发现控件已重绘并具有正确的边数。

若要更正此问题，请在 `FireViewChange` `IViewObjectExImpl` 设置边数后，添加对中定义的函数的调用。 如果控件在其自己的窗口中运行， `FireViewChange` 将直接调用 `InvalidateRect` 方法。 如果控件正在运行无窗口，则 `InvalidateRect` 将在容器的站点接口上调用方法。 这会强制控件重绘自身。

### <a name="to-add-a-call-to-fireviewchange"></a>添加对 FireViewChange 的调用

1. 通过将对的调用添加 `FireViewChange` 到方法来更新 polyctl.htm `put_Sides` 。 完成后，该 `put_Sides` 方法应如下所示：

    [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

添加后 `FireViewChange` ，重新生成并在 ActiveX 控件测试容器中再次尝试该控件。 这次，当您更改边数并单击时 `Invoke` ，您应立即看到控件更改。

在下一步中，你将添加一个事件。

[返回](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) 到步骤 3 &#124; [到步骤 5](../atl/adding-an-event-atl-tutorial-part-5.md)

## <a name="see-also"></a>请参阅

[教程](../atl/active-template-library-atl-tutorial.md)<br/>
[使用测试容器测试属性和事件](../mfc/testing-properties-and-events-with-test-container.md)
