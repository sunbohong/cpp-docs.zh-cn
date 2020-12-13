---
description: 了解详细信息：如何：使用颜色
title: 如何：使用颜色
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.color
- vc.editors.customcolorselector
- vc.editors.loadcolorpalette
- vc.editors.colorswindow
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
- Image editor [C++], colors
- colors [C++], Image editor
- colors [C++], image
- images [C++], colors
- Image editor [C++], colors
- Fill tool
- colors [C++], image
- images [C++], colors
- colors [C++], selection tools
- Image editor [C++], colors
- Select Color tool
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
- Image editor [C++], Colors Palette
- Colors Palette, Image editor
- colors [C++], inverting
- colors [C++]
- Color Indicator
- colors [C++], Colors window
- Colors window, hiding colors
- Show Colors Window command
- Colors window, displaying colors
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
- color palettes
- Load Palette Colors dialog box [C++]
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
- colors [C++], image
- Image editor [C++], color inversion
- images [C++], colors
- colors [C++], inverting
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
ms.openlocfilehash: 6c7d6ceaf2510d2360b32138735e8f61398da85a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135832"
---
# <a name="how-to-work-with-color"></a>如何：使用颜色

**图像编辑器** 包含许多专门处理和自定义颜色的功能。 可以设置前景色或背景色，使用颜色填充边界区域，或选择图像上的颜色作为当前前景色或背景色。 您可以使用 " [图像编辑器" 工具栏](./image-editor-for-icons.md) 上的工具以及 " **颜色** " 窗口中的 "颜色" 调色板来创建图像。

单色和16色图像的所有颜色都显示在 "**颜色**" 窗口的 "**颜色**" 面板中。 除了16种标准颜色之外，您还可以创建自己的自定义颜色。 更改调色板中的任何颜色会立即更改图像中的相应颜色。

使用256颜色图标和光标图像时，将使用 [属性窗口](/visualstudio/ide/reference/properties-window)中的 "**颜色**" 属性。 有关详细信息，请参阅 [创建256颜色图标或光标](./creating-an-icon-or-other-image-image-editor-for-icons.md)。

True-还可以创建彩色图像。 但是，在 " **颜色** " 窗口的 "完全调色板" 中看不到 "真彩色示例";它们仅出现在前景色或背景色指示器区域中。 使用 " **自定义颜色选择器** " 对话框创建真彩色。

可以在磁盘上保存自定义调色板，并根据需要重新加载它们。 您最近使用的调色板保存在注册表中，并在下一次启动 Visual Studio 时自动加载。

" **颜色** " 窗口包含两部分：

- **调色板**，这是表示可使用的颜色的颜色样本的数组。 使用图形工具时，可以选择示例来选择前景色和背景色。

- **颜色指示器**，显示屏幕和反转颜色的前景色和背景色以及选择器。

   ![Colors window](../windows/media/vccolorswindow.gif "vcColorsWindow")<br/>
   **颜色** 窗口

> [!NOTE]
> **屏幕颜色** 和 **反转颜色** 工具仅可用于图标和光标。

可以将 " **颜色** " 窗口与 " [图像编辑器" 工具栏](./image-editor-for-icons.md)一起使用。

- 若要显示 "**颜色**" 窗口，请在 "**图像编辑器**" 窗格中右键单击，然后选择 "**显示颜色窗口**" 或 "转向菜单 [图像](./image-editor-for-icons.md)  >  **显示颜色窗口**"。

- 若要隐藏 " **颜色** " 窗口，请取消固定窗口 (此操作将允许窗口在未使用时自动隐藏) 或选择 " **关闭** " 按钮。

**颜色** 调色板最初显示16种标准颜色。 对于显示的颜色，还可以创建自己的自定义颜色。 然后可保存和加载自定义的调色板。

使用 " **自定义颜色选择器** " 对话框，可以使用以下属性自定义用于映像的颜色：

|Property|描述|
|--------------------------|--------------------------|
|**渐变颜色显示**|更改所选颜色的值。<br/><br/>将十字线置于您要更改的颜色上，然后向上或向下移动滑块以更改颜色的亮度或 RGB 值。|
|**明度 Bar**|设置在 " **渐变颜色" 显示** 框中选择的颜色的发光度。<br/><br/>选择并向右拖动白色箭头以获得更高的亮度或缩小。 " **颜色** " 框显示您选择的颜色以及您设置的发光度的效果。|
|**颜色**|列出要定义的颜色的色调 (色轮值) 。 值介于0到240之间，其中0表示红色，60表示黄色，120为绿色，180表示绿色，200为洋红色，而240为蓝色。|
|**Hue**|列出要定义的颜色的色调 (色轮值) 。 值介于0到240之间，其中0表示红色，60表示黄色，120为绿色，180表示绿色，200为洋红色，而240为蓝色。|
|**饱和度**|指定正在定义的颜色的饱和度值。 饱和度是指指定色相的颜色量。 值介于0到240之间。|
|**亮度**|列出要定义的颜色的亮度 (亮度) 。 值介于0到240之间。|
|**Red**|指定正在定义的颜色的红色值。 值介于0到255之间。|
|**绿色**|指定正在定义的颜色的绿色值。 值介于0到255之间。|
|**蓝色**|指定正在定义的颜色的蓝色值。 值介于0到255之间。|

您可以保存和加载包含自 **定义颜色的调色板。** 默认情况下，当你启动 Visual Studio 时，会自动加载最近 **使用的调色板** 。

> [!TIP]
> 由于 **图像编辑器** 没有任何方法来还原默认的 **颜色** 调色板，因此应将默认的 **颜色** 调色板保存在 *标准 pal* 或 *默认* 的名称下，以便您可以轻松地还原默认设置。

使用 " **加载调色板颜色** " 对话框可以加载要在 c + + 项目中使用以下属性的特殊调色板：

|Property|描述|
|-----------------|-----------------|
|**Look in**|指定要查找文件或文件夹的位置。<br/><br/>选择箭头以选择其他位置，或在工具栏上选择文件夹图标以向上移动级别。|
|**文件名**|提供空间以键入要打开的文件的名称。<br/><br/>若要快速查找以前打开过的文件，请在下拉列表中选择文件名（如果可用）。<br/><br/>如果正在搜索某个文件，则可以使用星号 ( * ) 作为通配符。 例如，可以键入， \* \* 以查看所有文件的列表。 还可以键入文件的完整路径，例如， *C:\My Documents\MyColorPalette.pal* 或 *\\ \NetworkServer\MyFolder\MyColorPalette.pal*。|
|**文件类型**|列出要显示的文件类型。<br/><br/>调色板 ( * pal) 是调色板的默认文件类型。|

## <a name="how-to"></a>操作方式

### <a name="to-select-foreground-or-background-colors"></a>选择前景色或背景色

除 **橡皮擦** 外，当按下鼠标左键或右键时，" **图像编辑器** " 工具栏上的工具会绘制当前的前景色或背景色。

- 若要使用鼠标左键选择前景色，请在 " **颜色** " 调色板中选择所需的颜色。

- 若要使用鼠标右键选择背景色，请在 " **颜色** " 调色板中选择所需的颜色。

### <a name="to-fill-a-bounded-area-of-an-image-with-a-color"></a>使用颜色填充图像的限定区域

**图像编辑器** 提供了用当前绘图颜色或当前背景色填充包含的图像区域的 **填充** 工具。

### <a name="to-use-the-fill-tool"></a>使用填充工具

1. 使用 "**图像编辑器**" 工具栏或 "浏览  >  " "菜单" "图像 **工具**"，然后选择 "**填充**" 工具。

1. 如有必要，选择 "绘图颜色"。 在 " [颜色" 调色板](./image-editor-for-icons.md)中，选择鼠标左键以选择前景色或鼠标右键以选择背景色。

1. 将 **填充** 工具移动到要填充的区域。

1. 选择鼠标左键或右键，分别用前景色或背景色填充。

### <a name="to-pick-up-a-color-from-an-image-to-use-elsewhere"></a>从图像中选取要在其他位置使用的颜色

" **选择颜色**" 或 "颜色选取" 工具使图像上的任何颜色都为当前前景色或背景色，具体取决于按下的是鼠标左键还是鼠标右键。 若要取消 " **选择颜色** " 工具，请选择其他工具。

1. 使用 "**图像编辑器**" 工具栏或 "浏览  >  " "菜单" "图像 **工具**"，然后选择 "**选择颜色**" 工具。

1. 选择要从图像选取的颜色。

   > [!NOTE]
   > 选取颜色后， **图像编辑器** 会重新激活最近使用的工具。

1. 使用鼠标左键绘制前景色，或使用鼠标右键作为背景色。

### <a name="to-choose-the-background"></a>选择背景

在移动或复制图像中的选定内容时，所选内容中与当前背景色匹配的任何像素默认情况下都是透明的，它们不会在目标位置中遮盖像素。

可以从透明背景 (默认) 切换到不透明背景，并再次切换回来。 使用 "选择" 工具时，将在 "**图像编辑器**" 工具栏上的 **选项** 选择器中显示 **透明背景** 和不 **透明背景** 选项。

![后台选项 &#45; 不透明或透明](../windows/media/vcimageeditoropaqtranspback.gif "后台选项 &#45; 不透明或透明")<br/>
"**图像编辑器" 工具栏** 上的 **透明和不透明选项**

#### <a name="to-switch-between-a-transparent-and-opaque-background"></a>在透明和不透明背景之间切换

在 " **图像编辑器** " 工具栏中，选择 " **选项** 选择器"，然后选择适当的背景：

- 不 **透明背景 (O)**：现有图像被所选内容的所有部分遮盖。

- **透明背景 (T)**：现有图像通过与当前背景色匹配的选定部分显示。

> [!TIP]
> 对于快捷方式，请在 " **图像** " 菜单上选择或清除 " **绘图不透明**"。

选择已生效时，可以更改背景色，以更改图像的哪些部分是透明的。

### <a name="to-invert-the-colors-in-a-selection"></a>反转选定内容中的颜色

**图像编辑器** 提供了一种简便的方法来反转图像中选定部分的颜色，以便您可以了解图像如何以反转的颜色显示。

若要反转当前选定内容中的颜色，请参阅菜单 **图像**  >  **反转颜色**。

### <a name="to-customize-or-change-colors-on-the-colors-palette"></a>自定义或更改调色板的颜色

1. "中转到" 菜单 **图像**  >  **调整颜色**。

1. 在 " **自定义颜色选择器** " 对话框中，通过在相应的文本框中键入 RGB 或 HSL 值来定义颜色，或在 " **渐变颜色" 显示** 框中选择一种颜色。

1. 通过移动 **亮度** 栏上的滑块来设置发光度。

1. 许多自定义颜色是抖色。 如果希望纯色与抖动颜色最接近，请双击 **颜色** 框。

   如果以后决定要抖动颜色，请将滑块移动到 **明度** 栏上，或再次移动 " **渐变颜色" 显示** 框中的十字线以还原抖动。

1. 选择 **"确定"** 以添加新颜色。

### <a name="to-save-a-custom-colors-palette"></a>保存自定义调色板

1. 中转到菜单 **图像**  >  **保存调色板**。

1. 导航到要用于保存调色板的目录并键入调色板的名称。

1. 选择“保存”。

### <a name="to-load-a-custom-colors-palette"></a>加载自定义调色板

1. "中转到" 菜单 **图像**  >  **加载调色板**。

1. 在 " **加载调色板** " 对话框中，导航到正确的目录，然后选择要加载的调色板。 **调色板用** pal 文件扩展名保存。

## <a name="requirements"></a>要求

无

## <a name="see-also"></a>请参阅

[图标的图像编辑器](../windows/image-editor-for-icons.md)<br/>
[如何：创建图标或其他图像](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[如何：编辑图像](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[如何：使用绘图工具](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[加速键](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
