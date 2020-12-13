---
description: '了解详细信息：演练：更新 MFC 自由曲线应用程序 (第2部分) '
title: 演练：更新 MFC 随意画图应用程序（第 2 部分）
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: 2520ac8fc1c66a2fc388738d22f4851547b6d03b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142956"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>演练：更新 MFC 随意画图应用程序（第 2 部分）

本演练的[第1部分](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)演示了如何将 Office 熟知功能区添加到经典的自由曲线应用程序中。 本部分演示如何添加用户可以使用的功能区面板和控件，而不是菜单和命令。

## <a name="prerequisites"></a>先决条件

[Visual C++ 示例](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a> 个

本部分演练包含以下各节：

- [向功能区添加新面板](#addnewpanel)

- [向功能区添加 "帮助" 面板](#addhelppanel)

- [向功能区添加面板面板](#addpenpanel)

- [向功能区添加颜色按钮](#addcolorbutton)

- [向 Document 类添加 Color 成员](#addcolormember)

- [初始化笔并保存首选项](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a> 向功能区添加新面板

这些步骤显示了如何添加包含两个复选框的 **视图** 面板，这些复选框控制了工具栏和状态栏的可见性，以及一个 **窗口** 面板，其中包含一个垂直方向的拆分按钮，该按钮控制多文档界面 (MDI) windows 的创建和排列方式。

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>向功能区栏添加视图面板和窗口面板

1. 创建一个名为的面板 `View` ，其中有两个用于切换状态栏和工具栏的复选框。

   1. 从 " **工具箱**" 中，将 **面板** 拖到 **Home** 类别。 然后将两个 **复选框** 拖动到面板上。

   1. 单击面板来修改其属性。 将 **标题** 更改为 `View` 。

   1. 单击第一个复选框来修改其属性。 将 **ID** 更改为 `ID_VIEW_TOOLBAR` ，并将 **标题** 更改为 `Toolbar` 。

   1. 单击第二个复选框来修改其属性。 将 **ID** 更改为 `ID_VIEW_STATUS_BAR` ，并将 **标题** 更改为 `Status Bar` 。

1. 创建一个 `Window` 具有拆分按钮的名为的面板。 当用户单击 "拆分" 按钮时，快捷菜单会显示已在自由曲线应用程序中定义的三个命令。

   1. 从 " **工具箱**" 中，将 **面板** 拖到 **Home** 类别。 然后，将一个 **按钮** 拖到面板上。

   1. 单击面板来修改其属性。 将 **标题** 更改为 `Window` 。

   1. 单击按钮。 将 **标题** 更改为、对的 `Windows` **键** 进行更改， `w` 并将 `1` **拆分模式** 更改为 `False` 。 然后单击 **菜单项** 旁边的 **省略号 ("**) ，以打开"**项编辑器**"对话框。

   1. 单击 " **添加** 三次" 以添加三个按钮。

   1. 单击第一个按钮，然后将 **标题** 更改为 `New Window` ，将 **ID** 更改为 `ID_WINDOW_NEW` 。

   1. 单击第二个按钮，然后将 **标题** 更改为 `Cascade` ，将 **ID** 更改为 `ID_WINDOW_CASCADE` 。

   1. 单击第三个按钮，然后将 **标题** 更改为 `Tile` ，将 **ID** 更改为 `ID_WINDOW_TILE_HORZ` 。

1. 保存更改，然后生成并运行该应用程序。 应显示 **视图** 和 **窗口** 面板。 单击相应的按钮以确认它们是否正常工作。

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a> 向功能区添加 "帮助" 面板

现在，你可以将在自由曲线应用程序中定义的两个菜单项分配给名为 " **帮助主题** " 和 " **关于自由曲线**" 的功能区按钮。 这些按钮将添加到名为 **Help** 的新面板。

### <a name="to-add-a-help-panel"></a>添加 "帮助" 面板

1. 从 " **工具箱**" 中，将 **面板** 拖到 **Home** 类别。 然后将两个 **按钮** 拖到面板上。

1. 单击面板来修改其属性。 将 **标题** 更改为 `Help` 。

1. 单击第一个按钮。 将 **标题** 更改为 `Help Topics` ，并将 **ID** 更改为 `ID_HELP_FINDER` 。

1. 单击第二个按钮。 将 **标题** 更改为 `About Scribble...` ，并将 **ID** 更改为 `ID_APP_ABOUT` 。

1. 保存更改，然后生成并运行该应用程序。 应显示一个包含两个功能区按钮的 **帮助** 面板。

   > [!IMPORTANT]
   > 单击 " **帮助主题** " 按钮时，自由曲线应用程序将打开一个名为 *your_project_name*.chm 的压缩 HTML ( .chm) 帮助文件。 因此，如果你的项目未命名为 "自由曲线"，则必须将帮助文件重命名为你的项目名称。

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a> 向功能区添加面板面板

现在，添加一个面板用于显示控制笔粗细和颜色的按钮。 此面板包含一个复选框，该复选框在厚笔和薄笔之间切换。 其功能类似于自由曲线应用程序中 " **粗线条** " 菜单项的功能。

原始的自由曲线应用程序允许用户在用户单击菜单上的 " **笔宽度** " 时显示的对话框中选择 "笔宽度"。 由于功能区栏为新控件提供了足够的空间，因此可以通过使用功能区上的两个组合框来替换该对话框。 一个组合框调整细笔的宽度，另一个组合框调整厚笔的宽度。

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>向功能区添加笔面板和组合框

1. 从 " **工具箱**" 中，将 **面板** 拖到 **Home** 类别。 然后，将一个 **复选框** 和两个 **组合框** 拖到面板上。

1. 单击面板来修改其属性。 将 **标题** 更改为 `Pen` 。

1. 单击此复选框。 将 **标题** 更改为 `Use Thick` ，并将 **ID** 更改为 `ID_PEN_THICK_OR_THIN` 。

1. 单击第一个组合框。 将 **标题** 更改为 `Thin Pen` 、 **ID** 为 `ID_PEN_THIN_WIDTH` 、 **键入** 到、 `Drop List` **数据** 到 `1;2;3;4;5;6;7;8;9;` 和 **文本** `2` 。

1. 单击第二个组合框。 将 **标题** 更改为 `Thick Pen` 、 **ID** 为 `ID_PEN_THICK_WIDTH` 、 **键入** 到、 `Drop List` **数据** 到 `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;` 和 **文本** `5` 。

1. 新组合框与任何现有菜单项都不对应，因此必须为每个笔选项创建一个菜单项。

   1. 在 " **资源视图** " 窗口中，打开 **IDR_SCRIBBTYPE** "菜单" 资源。

   1. 单击 " **笔** " 以打开 "笔" 菜单。 然后单击 " **在此处键入** " 并键入 `Thi&n Pen` 。

   1. 右键单击您键入的文本以打开 " **属性** " 窗口，然后将 "ID" 属性更改为 `ID_PEN_THIN_WIDTH` 。

   1. 为每个笔菜单项创建一个事件处理程序。 右键单击所创建的 " **Thi&n" 笔** 菜单项，然后单击 " **添加事件处理程序**"。 将显示 " **事件处理程序向导** "。

   1. 在向导的 " **类" 列表** 框中，选择 " **CScribbleDoc** "，然后单击 "添加" **和 "编辑**"。 命令创建一个名为的事件处理程序 `CScribbleDoc::OnPenThinWidth` 。

   1. 将以下代码添加到 `CScribbleDoc::OnPenThinWidth`。

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        // Get a pointer to the Thin Width combo box
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
        CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

        //Get the selected value
        int nCurSel = pThinComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 接下来，为厚笔创建菜单项和事件处理程序。

   1. 在 " **资源视图** " 窗口中，打开 **IDR_SCRIBBTYPE** "菜单" 资源。

   1. 单击 " **笔** " 以打开 "笔" 菜单。 然后单击 " **在此处键入** " 并键入 `Thic&k Pen` 。

   1. 右键单击您键入的文本以显示 " **属性** " 窗口。 将 ID 属性更改为 `ID_PEN_THICK_WIDTH` 。

   1. 右键单击您创建的 " **厚墨** " 菜单项，然后单击 " **添加事件处理程序**"。 将显示 " **事件处理程序向导** "。

   1. 在向导的 " **类" 列表** 框中，选择 " **CScribbleDoc** "，然后单击 "添加" **和 "编辑**"。 命令创建一个名为的事件处理程序 `CScribbleDoc::OnPenThickWidth` 。

   1. 将以下代码添加到 `CScribbleDoc::OnPenThickWidth`。

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
            CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
        // Get the selected value
        int nCurSel = pThickComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 保存更改，然后生成并运行该应用程序。 应显示新的按钮和组合框。 尝试使用不同的笔宽自由绘制。

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a> 将颜色按钮添加到 "笔" 面板

接下来，添加一个 [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) 对象，该对象可让用户以彩色随意绘制。

### <a name="to-add-a-color-button-to-the-pen-panel"></a>将颜色按钮添加到 "笔" 面板

1. 添加颜色按钮之前，请为其创建菜单项。 在 " **资源视图** " 窗口中，打开 **IDR_SCRIBBTYPE** "菜单" 资源。 单击 " **笔** " 菜单项以打开 "笔" 菜单。 然后单击 " **在此处键入** " 并键入 `&Color` 。 右键单击您键入的文本以显示 " **属性** " 窗口。 将 ID 更改为 `ID_PEN_COLOR`。

1. 现在，请添加颜色按钮。 从 " **工具箱**" 中，将 " **颜色" 按钮** 拖动到 " **笔** " 面板。

1. 单击 "颜色" 按钮。 将 **标题** 更改为、 `Color` **ID** 为 `ID_PEN_COLOR` 、 **简单查找** 到 `True` 、对的 **大型图像索引** `1` 以及 **拆分模式** `False` 。

1. 保存更改，然后生成并运行该应用程序。 " **笔** " 面板上应显示 "新建颜色" 按钮。 但是，不能使用该函数，因为它还没有事件处理程序。 接下来的步骤演示如何为颜色按钮添加事件处理程序。

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a> 向 Document 类添加 Color 成员

由于原始随意画图应用程序没有颜色笔，因此必须为其编写一个实现。 若要存储文档的笔颜色，请将一个新成员添加到文档类中 `CscribbleDoc` 。

### <a name="to-add-a-color-member-to-the-document-class"></a>向 document 类添加颜色成员

1. 在 scribdoc 的类中， `CScribbleDoc` 找到 `// Attributes` 部分。 在定义数据成员后添加以下代码行 `m_nThickWidth` 。

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. 每个文档都包含用户已绘制的 stokes 新的列表。 每个笔划由对象定义 `CStroke` 。 `CStroke`类不包括有关笔颜色的信息，因此您必须修改类。 在 scribdoc 的类中， `CStroke` 将以下代码行添加到 `m_nPenWidth` 数据成员定义之后。

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. 在 scribdoc 中，添加一个新的 `CStroke` 构造函数，该构造函数的参数指定宽度和颜色。 在语句后添加以下代码行 `CStroke(UINT nPenWidth);` 。

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. 在 scribdoc 中，添加新 `CStroke` 构造函数的实现。 在构造函数的实现之后添加以下代码 `CStroke::CStroke(UINT nPenWidth)` 。

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. 按如下所示更改方法的第二行 `CStroke::DrawStroke` 。

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. 设置文档类的默认笔颜色。 在 scribdoc 中，将以下行添加到 `CScribbleDoc::InitDocument` 语句后面的 `m_nThickWidth = 5;` 。

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. 在 scribdoc 中，将方法的第一行更改 `CScribbleDoc::NewStroke` 为以下项。

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. 将方法的最后一行更改 `CScribbleDoc::ReplacePen` 为以下项。

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. 您 `m_penColor` 在上一步中添加了成员。 现在，为设置成员的 "颜色" 按钮创建一个事件处理程序。

   1. 在 " **资源视图** " 窗口中，打开 IDR_SCRIBBTYPE "菜单" 资源。

   1. 右键单击 " **颜色** " 菜单项，然后单击 " **添加事件处理程序**"。 此时将显示 " **事件处理程序向导** "。

   1. 在向导的 " **类" 列表** 框中，选择 " **CScribbleDoc** "，然后单击 "添加" **和 "编辑** " 按钮。 命令创建 `CScribbleDoc::OnPenColor` 事件处理程序存根。

1. 将事件处理程序的存根替换为 `CScribbleDoc::OnPenColor` 以下代码。

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

1. 保存更改，然后生成并运行应用程序。 现在，可以按 "颜色" 按钮并更改笔的颜色。

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a> 初始化笔并保存首选项

接下来，初始化笔的颜色和宽度。 最后，从文件保存和加载颜色绘图。

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>在功能区栏上初始化控件

1. 在功能区栏上初始化钢笔。

   在方法中，将以下代码添加到 `CScribbleDoc::InitDocument` 语句后面的 scribdoc。 `m_sizeDoc = CSize(200,200)`

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

1. 将颜色绘图保存到文件。 在方法中，将以下语句添加到 `CStroke::Serialize` 语句后面的 scribdoc。 `ar << (WORD)m_nPenWidth;`

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. 最后，从文件加载颜色绘制。 在方法中的语句后添加以下代码行 `CStroke::Serialize` `m_nPenWidth = w;` 。

   ```cpp
   ar >> m_penColor;
   ```

1. 现在，使用彩色涂抹，并将绘图保存到文件。

## <a name="conclusion"></a>结论

已更新 MFC 自由曲线应用程序。 修改现有应用程序时，请使用本演练作为指导。

## <a name="see-also"></a>请参阅

[演练](../mfc/walkthroughs-mfc.md)<br/>
[演练：更新 MFC 自由曲线应用程序 (第1部分) ](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
