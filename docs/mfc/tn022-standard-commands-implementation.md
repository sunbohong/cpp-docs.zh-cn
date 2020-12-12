---
description: 了解详细信息： TN022：标准命令实现
title: TN022：标准命令实现
ms.date: 11/04/2016
f1_keywords:
- vc.commands
helpviewer_keywords:
- ID_PREV_PANE command [MFC]
- ID_APP_EXIT command [MFC]
- ID_NEXT_PANE command [MFC]
- ID_INDICATOR_REC command [MFC]
- ID_WINDOW_SPLIT command [MFC]
- ID_FILE_PRINT_PREVIEW command [MFC]
- ID_WINDOW_CASCADE command [MFC]
- ID_FILE_CLOSE command [MFC]
- ID_FILE_SAVE_COPY_AS command [MFC]
- ID_WINDOW_ARRANGE command [MFC]
- ID_EDIT_FIND command [MFC]
- ID_FILE_OPEN command [MFC]
- ID_FILE_PAGE_SETUP command [MFC]
- ID_OLE_VERB_FIRST command [MFC]
- ID_EDIT_UNDO command [MFC]
- ID_EDIT_CLEAR command [MFC]
- ID_INDICATOR_CAPS command [MFC]
- ID_HELP_INDEX command [MFC]
- commands [MFC], standard
- ID_FILE_PRINT_SETUP command [MFC]
- ID_DEFAULT_HELP command [MFC]
- ID_INDICATOR_SCRL command [MFC]
- ID_FILE_PRINT command [MFC]
- ID_INDICATOR_OVR command [MFC]
- ID_INDICATOR_KANA command [MFC]
- ID_EDIT_COPY command [MFC]
- ID_EDIT_REDO command [MFC]
- ID_EDIT_PASTE command [MFC]
- ID_OLE_INSERT_NEW command [MFC]
- ID_OLE_EDIT_LINKS command [MFC]
- ID_EDIT_PASTE_SPECIAL command [MFC]
- ID_INDICATOR_EXT command [MFC]
- ID_HELP_USING command [MFC]
- standard commands
- ID_VIEW_STATUS_BAR command [MFC]
- ID_FILE_SAVE_AS command [MFC]
- ID_EDIT_CLEAR_ALL command [MFC]
- ID_WINDOW_NEW command [MFC]
- ID_CONTEXT_HELP command [MFC]
- ID_EDIT_REPLACE command [MFC]
- ID_WINDOW_TILE_HORZ command [MFC]
- ID_APP_ABOUT command [MFC]
- TN022
- ID_VIEW_TOOLBAR command [MFC]
- ID_HELP command [MFC]
- ID_WINDOW_TILE_VERT command [MFC]
- ID_EDIT_CUT command [MFC]
- ID_FILE_UPDATE command [MFC]
- ID_EDIT_REPEAT command [MFC]
- ID_FILE_SAVE command [MFC]
- ID_EDIT_PASTE_LINK command [MFC]
- ID_EDIT_SELECT_ALL command [MFC]
- ID_FILE_NEW command [MFC]
- ID_INDICATOR_NUM command
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
ms.openlocfilehash: 7c8540dcf0e41e5f6d5f00a4f22568c4df0fcdbe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215802"
---
# <a name="tn022-standard-commands-implementation"></a>TN022：标准命令实现

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

此注释描述 MFC 2.0 提供的标准命令实现。 首先阅读 [技术说明 21](../mfc/tn021-command-and-message-routing.md) ，因为它描述了用于实现许多标准命令的机制。

此说明假设了解 MFC 体系结构、Api 和常见编程做法。 还介绍了已记录的 "仅实现实现" Api。 这并不是开始学习的功能，或者如何在 MFC 中进行编程。 有关更多常规信息以及记录的 Api 的详细信息，请参阅 Visual C++。

## <a name="the-problem"></a>问题

MFC 在头文件 AFXRES.H 中定义了许多标准命令 Id。 此类命令的框架支持有所不同。 了解框架类处理这些命令的位置和方式不仅会向您展示框架如何在内部工作，还会提供有关如何自定义标准实现的有用信息，并教您实现自己的命令处理程序的几种方法。

## <a name="contents-of-this-technical-note"></a>本技术说明的内容

每个命令 ID 分为两部分：

- 标题：命令 ID 的符号名称 (例如，ID_FILE_SAVE) 后跟命令的用途 (例如，"保存当前文档" ) 以冒号分隔。

- 描述哪些类实现命令以及默认实现功能的一个或多个段落

大多数默认的命令实现在框架的基类消息映射中是 prewired 的。 有些命令实现需要派生类中的显式布线。 这些是在 "Note" 下描述的。 如果在应用程序向导中选择了正确的选项，则会在生成的主干应用程序中为你连接这些默认处理程序。

## <a name="naming-convention"></a>命名约定

标准命令遵循一个简单的命名约定，如果可能，我们建议你使用。 大多数标准命令位于应用程序菜单栏中的标准位置。 命令的符号名称以 "ID_" 开头，后跟标准弹出菜单名称，然后是菜单项名称。 符号名称为大写，带有下划线单词分隔符。 对于没有标准菜单项名称的命令，逻辑命令名称是以 "ID_" 开头的 (例如，ID_NEXT_PANE) 。

使用前缀 "ID_" 来指示设计为绑定到菜单项、工具栏按钮或其他命令用户界面对象的命令。 处理 "ID_" 命令的命令处理程序应使用 MFC 命令体系结构的 ON_COMMAND 和 ON_UPDATE_COMMAND_UI 机制。

建议对不遵循命令体系结构的菜单项使用标准的 "IDM_" 前缀，并需要特定于菜单的代码来启用和禁用它们。 当然，菜单特定命令的数量应该很小，因为在执行 MFC 命令体系结构时，不仅会使命令处理程序功能更强大， (因为它们将与工具栏一起使用) 但使命令处理程序代码可重复使用。

## <a name="id-ranges"></a>ID 范围

有关在 MFC 中使用 ID 范围的详细信息，请参阅 [技术说明 20](../mfc/tn020-id-naming-and-numbering-conventions.md) 。

MFC 标准命令的范围是0xE000 到0xEFFF。 请不要依赖于这些 Id 的特定值，因为它们在库的未来版本中可能会更改。

应用程序应在0x8000 到0xDFFF 的范围内定义其命令。

## <a name="standard-command-ids"></a>标准命令 Id

对于每个命令 ID，都有一个可在文件提示中找到的标准消息行提示字符串。.RC. 该菜单提示符的字符串 ID 必须与命令 ID 的字符串 ID 相同。

- ID_FILE_NEW 创建新的/空文档。

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   `CWinApp::OnFileNew` 根据应用程序中的文档模板数，以不同的方式实现此命令。 如果只有一个，则 `CDocTemplate` `CWinApp::OnFileNew` 将创建该类型的新文档以及正确的框架和视图类。

   如果有多个，则 `CDocTemplate` `CWinApp::OnFileNew` 会提示用户提供一个对话框 (AFX_IDD_NEWTYPEDLG) 让他们选择要使用的文档类型。 所选的 `CDocTemplate` 用于创建文档。

   ID_FILE_NEW 的一种常见自定义是提供不同、更图形的文档类型选择。 在这种情况下，你可以自行实现 `CMyApp::OnFileNew` 并将其放置在消息映射中，而不是 `CWinApp::OnFileNew` 。 无需调用基类实现。

   ID_FILE_NEW 的另一个常见的自定义是提供单独的命令来创建每种类型的文档。 在这种情况下，应该定义新的命令 Id，例如 ID_FILE_NEW_CHART 和 ID_FILE_NEW_SHEET。

- ID_FILE_OPEN 打开现有文档。

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   `CWinApp::OnFileOpen` 具有一个非常简单的调用实现， `CWinApp::DoPromptFileName` 后跟 `CWinApp::OpenDocumentFile` 要打开的文件的文件名或路径名称。 `CWinApp`实现例程显示 `DoPromptFileName` 标准的 FileOpen 对话框，并用从当前文档模板获取的文件扩展名对其进行填充。

   ID_FILE_OPEN 的一种常见自定义是自定义 FileOpen 对话框或添加其他文件筛选器。 自定义此方法的建议方法是将默认实现替换为自己的 FileOpen 对话框，并 `CWinApp::OpenDocumentFile` 使用文档的文件或路径名称调用。 无需调用基类。

- ID_FILE_CLOSE 关闭当前打开的文档。

   `CDocument::OnFileClose` 调用 `CDocument::SaveModified` 以提示用户保存文档（如果文档已修改），然后调用 `OnCloseDocument` 。 所有结束逻辑（包括销毁文档）都是在例程中完成的 `OnCloseDocument` 。

    > [!NOTE]
    >  ID_FILE_CLOSE 的行为不同于发送到 "文档框架" 窗口的 WM_CLOSE 消息或 SC_CLOSE 系统命令。 关闭窗口只会关闭文档，这是显示文档的最后一个框架窗口。 用 ID_FILE_CLOSE 关闭文档不仅会关闭文档，还会关闭显示文档的所有框架窗口。

- ID_FILE_SAVE 保存当前文档。

   实现使用用于 `CDocument::DoSave` 和的 helper 例程 `OnFileSave` `OnFileSaveAs` 。 如果在 (之前保存尚未保存的文档，则该文档不具有路径名称（如 FileNew) 或从只读文档中读取的文件），该 `OnFileSave` 逻辑的作用类似于 ID_FILE_SAVE_AS 命令并要求用户提供新的文件名。 打开该文件并执行保存操作的实际过程是通过虚拟功能完成的 `OnSaveDocument` 。

   自定义 ID_FILE_SAVE 有两个常见的原因。 对于不保存的文档，只需从用户界面中删除 ID_FILE_SAVE 菜单项和工具栏按钮。 另外，请确保永远不要对文档进行脏 (也就是说，绝不会调用 `CDocument::SetModifiedFlag`) ，框架将永远不会导致文档保存。 对于保存到磁盘文件以外的其他位置的文档，请为该操作定义新的命令。

   对于 `COleServerDoc` ，ID_FILE_SAVE 会同时用于文件保存 (对于普通文档) 和 (适用于嵌入文档) 的文件更新。

   如果您的文档数据存储在单独的磁盘文件中，但您不想使用默认 `CDocument` 序列化实现，则应重写 `CDocument::OnSaveDocument` 而不是 `OnFileSave` 。

- ID_FILE_SAVE_AS 将当前文档另存为其他文件名。

   `CDocument::OnFileSaveAs`实现使用与相同的 `CDocument::DoSave` helper 例程 `OnFileSave` 。 此 `OnFileSaveAs` 命令的处理方式与 ID_FILE_SAVE 如果文档在保存之前没有文件名。 `COleServerDoc::OnFileSaveAs` 实现逻辑以保存普通文档数据文件，或将表示作为其他应用程序嵌入的 OLE 对象的服务器文档另存为单独的文件。

   如果自定义 ID_FILE_SAVE 的逻辑，则可能要以类似的方式自定义 ID_FILE_SAVE_AS 或 "另存为" 操作可能不适用于您的文档。 如果菜单栏不需要，则可以将其从菜单栏中删除。

- ID_FILE_SAVE_COPY_AS 使用新名称保存复制当前文档。

   `COleServerDoc::OnFileSaveCopyAs`实现非常类似于 `CDocument::OnFileSaveAs` ，只不过保存后文档对象未 "附加到基础文件。 也就是说，如果在保存之前 "修改" 了内存中文档，则该文档仍为 "已修改"。 此外，此命令对文档中存储的路径名称或标题没有影响。

- ID_FILE_UPDATE 通知容器保存嵌入文档。

   `COleServerDoc::OnUpdateDocument`实现只是 notifiies 要保存嵌入的容器。 然后，容器将调用相应的 OLE Api 来保存嵌入的对象。

- ID_FILE_PAGE_SETUP 调用特定于应用程序的页面设置/布局对话框。

   此对话框目前没有标准，并且该框架没有此命令的默认实现。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_FILE_PRINT_SETUP 调用标准的 "打印设置" 对话框。

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   此命令将调用标准的 "打印设置" 对话框，该对话框允许用户为至少此文档或此应用程序中的所有文档自定义打印机和打印设置。 必须使用 "控制面板" 更改整个系统的默认打印机设置。

   `CWinApp::OnFilePrintSetup` 具有一个非常简单的实现，该实现创建 `CPrintDialog` 对象并调用 `CWinApp::DoPrintDialog` 实现函数。 这将设置应用程序默认打印机设置。

   自定义此命令的常见需求是允许每个文档的打印机设置，保存时这些设置应随文档一起存储。 若要执行此操作，应在类中添加一个消息映射处理程序，该处理程序用于 `CDocument` 创建 `CPrintDialog` 对象，并使用适当的打印机属性（ (通常 *hDevMode* 和 *hDevNames*) ）对其进行初始化，调用 `CPrintDialog::DoModal` ，并保存更改后的打印机设置。 对于可靠的实现，应查看的实现， `CWinApp::DoPrintDialog` 以检测错误并 `CWinApp::UpdatePrinterSelection` 处理合理的默认值和跟踪系统范围内的打印机更改。

- 当前文档 ID_FILE_PRINT 标准打印

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CView` 派生类的消息映射。

   此命令打印当前文档或更正确地启动打印过程，这涉及调用标准打印对话框并运行打印引擎。

   `CView::OnFilePrint` 实现此命令和主打印循环。 它调用虚拟 `CView::OnPreparePrinting` 以通过 "打印" 对话框提示用户。 然后，它准备要转到打印机的输出 DC，使打印进度对话框 (AFX_IDD_PRINTDLG) ，并将 `StartDoc` 转义发送到打印机。 `CView::OnFilePrint` 还包含面向页面的母版页打印循环。 对于每个页，它会调用虚拟， `CView::OnPrepareDC` 后跟 `StartPage` 转义并 `CView::OnPrint` 为该页调用虚拟。 完成后，将 `CView::OnEndPrinting` 调用虚拟，并关闭 "打印进度" 对话框。

   MFC 打印体系结构旨在以多种不同的方式挂钩打印和打印预览。 通常，您将发现各种可 `CView` 重写函数对于任何面向页面的打印任务都足够了。 仅在将打印机用于非页面面向的输出的情况下，如果你发现需要替换 ID_FILE_PRINT 实现。

- ID_FILE_PRINT_PREVIEW 为当前文档输入打印预览模式。

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CView` 派生类的消息映射。

   `CView::OnFilePrintPreview` 通过调用记录的 helper 函数，启动 "打印预览" 模式 `CView::DoPrintPreview` 。 `CView::DoPrintPreview` 是 print preview 循环的主引擎，就像 `OnFilePrint` 打印循环的主引擎一样。

   可以通过将不同参数传递给，以多种方式自定义打印预览操作 `DoPrintPreview` 。 请参阅 [技术说明 30](../mfc/tn030-customizing-printing-and-print-preview.md)，其中讨论了打印预览的一些详细信息以及如何对其进行自定义。

- ID_FILE_MRU_FILE1 .。。FILE16 文件 MRU **列表** 的一系列命令 id。

   `CWinApp::OnUpdateRecentFileMenu` 是一个更新命令 UI 处理程序，它是 ON_UPDATE_COMMAND_UI 机制的更高级使用之一。 在菜单资源中，只需使用 ID ID_FILE_MRU_FILE1 定义单个菜单项。 该菜单项最初处于禁用状态。

   当 MRU 列表增大时，将在列表中添加更多菜单项。 标准 `CWinApp` 实现默认为四个最近使用的文件的标准限制。 可以通过 `CWinApp::LoadStdProfileSettings` 使用更大或更小的值调用来更改默认值。 MRU 列表存储在应用程序的中。INI 文件。 如果调用，则该列表将加载到应用程序的 `InitInstance` 函数中 `LoadStdProfileSettings` ，并且在应用程序退出时保存。 MRU 更新命令 UI 处理程序还会将绝对路径转换为相对路径，以便在 "文件" 菜单上显示。

   `CWinApp::OnOpenRecentFile` 执行实际命令的 ON_COMMAND 处理程序。 它只是从 MRU 列表中获取文件名，并调用 `CWinApp::OpenDocumentFile` ，该文件执行打开文件和更新 MRU 列表的所有工作。

   不建议自定义此命令处理程序。

- ID_EDIT_CLEAR 清除当前选定内容

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 使用提供此命令的实现 `CEdit::Clear` 。 如果当前没有选定内容，将禁用该命令。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_CLEAR_ALL 清除整篇文档。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   如果你选择实现此命令，则建议你使用此命令 ID。 有关示例实现，请参阅 MFC 教程示例 [自由曲线](../overview/visual-cpp-samples.md) 。

- ID_EDIT_COPY 将当前选定内容复制到剪贴板。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 提供此命令的实现，该实现将当前选定文本复制到剪贴板，CF_TEXT 使用 `CEdit::Copy` 。 如果当前没有选定内容，将禁用该命令。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_CUT 将当前所选内容剪切到剪贴板。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 提供此命令的实现，该实现将当前选定文本作为 CF_TEXT 使用剪切到剪贴板 `CEdit::Cut` 。 如果当前没有选定内容，将禁用该命令。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_FIND 开始查找操作，会打开无模式查找对话框。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 提供此命令的一个实现，该实现调用实现 helper 函数 `OnEditFindReplace` 以使用并存储私有实现变量中的前一个查找/替换设置。 `CFindReplaceDialog`类用于管理提示用户的无模式对话框。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_PASTE 插入当前剪贴板内容。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 提供此命令的实现，该实现使用复制替换所选文本的当前剪贴板数据 `CEdit::Paste` 。 如果剪贴板中没有 **CF_TEXT** ，则该命令处于禁用状态。

   `COleClientDoc` 只需为此命令提供更新命令 UI 处理程序。 如果剪贴板中不包含可嵌入的 OLE 项/对象，则该命令将处于禁用状态。 您负责为实际命令编写处理程序，以执行实际粘贴。 如果您的 OLE 应用程序还可以粘贴其他格式，则您应该在您的视图或文档中提供自己的更新命令 UI 处理程序， (就是在 `COleClientDoc` 命令目标路由) 之前的某个位置。

   如果你选择实现此命令，则建议你使用此命令 ID。

   若要替换标准 OLE 实现，请使用 `COleClientItem::CanPaste` 。

- ID_EDIT_PASTE_LINK 插入来自当前剪贴板内容的链接。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `COleDocument` 只需为此命令提供更新命令 UI 处理程序。 如果剪贴板不包含可链接 OLE 项/对象，则将禁用该命令。 您负责为实际命令编写处理程序，以执行实际粘贴。 如果您的 OLE 应用程序还可以粘贴其他格式，则您应该在您的视图或文档中提供自己的更新命令 UI 处理程序， (就是在 `COleDocument` 命令目标路由) 之前的某个位置。

   如果你选择实现此命令，则建议你使用此命令 ID。

   若要替换标准 OLE 实现，请使用 `COleClientItem::CanPasteLink` 。

- ID_EDIT_PASTE_SPECIAL 用选项插入当前剪贴板内容。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。 MFC 不提供此对话框。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_REPEAT 重复上一个操作。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 提供此命令的实现以重复最后一个查找操作。 使用最后一个查找的私有实现变量。 如果无法尝试查找，将禁用该命令。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_REPLACE 开始替换操作，将显示 "无模式替换" 对话框。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 提供此命令的一个实现，该实现调用实现 helper 函数 `OnEditFindReplace` 以使用并存储私有实现变量中的前一个查找/替换设置。 `CFindReplaceDialog`类用于管理提示用户的无模式对话框。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_SELECT_ALL 选择整个文档。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 提供此命令的实现，该实现选择文档中的所有文本。 如果没有要选择的文本，将禁用该命令。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_UNDO 撤消上一个操作。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   `CEditView` 使用提供此命令的实现 `CEdit::Undo` 。 如果返回 FALSE，则禁用该命令 `CEdit::CanUndo` 。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_EDIT_REDO 重复上一个操作。

   当前没有此命令的标准实现。 必须为每个 `CView` 派生类实现此类。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_WINDOW_NEW 在活动文档上打开另一个窗口。

   `CMDIFrameWnd::OnWindowNew` 通过使用当前文档的文档模板来创建另一个包含当前文档的另一个视图的框架，实现此功能强大的功能。

   与大多数文档界面 (MDI) Window 菜单命令一样，如果没有活动的 MDI 子窗口，该命令会被禁用。

   不建议自定义此命令处理程序。 如果希望提供创建其他视图或框架窗口的命令，可能更好发明自己的命令。 你可以从中克隆代码 `CMDIFrameWnd::OnWindowNew` ，并将其修改为特定的帧并查看你喜欢的类。

- ID_WINDOW_ARRANGE 在 MDI 窗口底部排列图标。

   `CMDIFrameWnd` 在实现 helper 函数中实现此标准 MDI 命令 `OnMDIWindowCmd` 。 此帮助程序将命令 Id 映射到 MDI Windows 消息，并因此可以共享大量代码。

   与大多数 MDI 窗口菜单命令一样，如果没有活动的 MDI 子窗口，该命令会被禁用。

   不建议自定义此命令处理程序。

- ID_WINDOW_CASCADE 层叠窗口，使它们重叠。

   `CMDIFrameWnd` 在实现 helper 函数中实现此标准 MDI 命令 `OnMDIWindowCmd` 。 此帮助程序将命令 Id 映射到 MDI Windows 消息，并因此可以共享大量代码。

   与大多数 MDI 窗口菜单命令一样，如果没有活动的 MDI 子窗口，该命令会被禁用。

   不建议自定义此命令处理程序。

- ID_WINDOW_TILE_HORZ 水平平铺窗口。

   与 ID_WINDOW_CASCADE 一样，此命令是在中实现的 `CMDIFrameWnd` ，但不同的 MDI Windows 消息用于操作。

   应为应用程序选取默认的平铺方向。 为此，可以将窗口 "磁贴" 菜单项的 ID 更改为 ID_WINDOW_TILE_HORZ 或 ID_WINDOW_TILE_VERT。

- ID_WINDOW_TILE_VERT 垂直平铺窗口。

   与 ID_WINDOW_CASCADE 一样，此命令是在中实现的 `CMDIFrameWnd` ，但不同的 MDI Windows 消息用于操作。

   应为应用程序选取默认的平铺方向。 为此，可以将窗口 "磁贴" 菜单项的 ID 更改为 ID_WINDOW_TILE_HORZ 或 ID_WINDOW_TILE_VERT。

- ID_WINDOW_SPLIT 键盘接口到拆分器。

   `CView` 为实现处理此命令 `CSplitterWnd` 。 如果视图是拆分窗口的一部分，则此命令将委托给实现函数 `CSplitterWnd::DoKeyboardSplit` 。 这会将拆分器置于允许键盘用户拆分或撤消拆分窗口的模式下。

   如果视图不在拆分器中，则此命令处于禁用状态。

   不建议自定义此命令处理程序。

- ID_APP_ABOUT 调用 "关于" 对话框。

   应用程序的 "关于" 框没有标准实现。 默认的应用程序向导创建的应用程序将为您的应用程序创建一个自定义对话框类，并将其用作您的 "关于" 框。 向导还将编写处理此命令并调用对话框的普通命令处理程序。

   你几乎始终实现此命令。

- ID_APP_EXIT 退出应用程序。

   `CWinApp::OnAppExit` 通过向应用程序的主窗口发送 WM_CLOSE 消息来处理此命令。 应用程序关闭应用程序 (提示输入脏文件，等等) 由实现进行处理 `CFrameWnd` 。

   不建议自定义此命令处理程序。 建议重写 `CWinApp::SaveAllModified` 或 `CFrameWnd` 关闭逻辑。

   如果你选择实现此命令，则建议你使用此命令 ID。

- ID_HELP_INDEX 列出了中的帮助主题。.HLP 文件。

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   `CWinApp::OnHelpIndex` 通过完全调用来处理此命令 `CWinApp::WinHelp` 。

   不建议自定义此命令处理程序。

- ID_HELP_USING 显示有关如何使用帮助的帮助。

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   `CWinApp::OnHelpUsing` 通过完全调用来处理此命令 `CWinApp::WinHelp` 。

   不建议自定义此命令处理程序。

- ID_CONTEXT_HELP 进入 SHIFT + F1 帮助模式。

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   `CWinApp::OnContextHelp` 通过以下方法来处理此命令：设置帮助模式光标，输入模式循环，并等待用户选择窗口以获得帮助。 有关 MFC 帮助实现的更多详细信息，请参阅 [技术说明 28](../mfc/tn028-context-sensitive-help-support.md) 。

   不建议自定义此命令处理程序。

- ID_HELP 提供有关当前上下文的帮助

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   `CWinApp::OnHelp` 通过获取当前应用程序上下文的正确帮助上下文来处理此命令。 这将处理简单的 F1 帮助、有关消息框等的帮助。 有关 MFC 帮助实现的更多详细信息，请参阅 [技术说明 28](../mfc/tn028-context-sensitive-help-support.md) 。

   不建议自定义此命令处理程序。

- ID_DEFAULT_HELP 显示上下文的默认帮助

    > [!NOTE]
    >  若要启用此功能，必须将此连接到 `CWinApp` 派生类的消息映射。

   此命令通常映射到 `CWinApp::OnHelpIndex` 。

   如果默认帮助和帮助索引之间需要区分，则可以提供不同的命令处理程序。

- ID_NEXT_PANE 转到下一个窗格

   `CView` 为实现处理此命令 `CSplitterWnd` 。 如果视图是拆分窗口的一部分，则此命令将委托给实现函数 `CSplitterWnd::OnNextPaneCmd` 。 这会将活动视图移动到拆分器中的下一个窗格。

   如果视图不在拆分器中或没有下一个要执行的窗格，则将禁用此命令。

   不建议自定义此命令处理程序。

- ID_PREV_PANE 转到上一个窗格

   `CView` 为实现处理此命令 `CSplitterWnd` 。 如果视图是拆分窗口的一部分，则此命令将委托给实现函数 `CSplitterWnd::OnNextPaneCmd` 。 这会将活动视图移动到拆分器中的上一个窗格。

   如果视图不在拆分器中或没有上一个窗格可供使用，则将禁用此命令。

   不建议自定义此命令处理程序。

- ID_OLE_INSERT_NEW 插入新的 OLE 对象

   当前没有此命令的标准实现。 必须为派生类实现此 `CView` 目的，才能在当前选定内容中插入新的 OLE 项/对象。

   所有 OLE 客户端应用程序都应实现此命令。 使用 OLE 选项的执行程序，将在你的视图类中创建一个你需要完成的框架实现 `OnInsertObject` 。

   有关此命令的完整实现，请参阅 MFC OLE 示例 [OCLIENT](../overview/visual-cpp-samples.md) 示例。

- ID_OLE_EDIT_LINKS 编辑 OLE 链接

   `COleDocument` 使用 MFC 提供的标准 OLE 链接对话框实现来处理此命令。 此对话框的实现通过 `COleLinksDialog` 类访问。 如果当前文档不包含任何链接，则禁用该命令。

   不建议自定义此命令处理程序。

- ID_OLE_VERB_FIRST .。。OLE 谓词的最后一个 ID 范围

   `COleDocument` 对于当前选定的 OLE 项/对象支持的谓词，使用此命令 ID 范围。 这必须是一个范围，因为给定的 OLE 项/对象类型可以支持零个或多个自定义谓词。 在应用程序的菜单中，应具有一个 ID 为 ID_OLE_VERB_FIRST 的菜单项。 当程序运行时，将用适当的菜单谓词说明更新菜单， (或弹出菜单中具有许多谓词) 。 OLE 菜单的管理由处理 `AfxOleSetEditMenu` ，该操作在此命令的 update 命令 UI 处理程序中完成。

   没有用于处理此范围内的每个命令 ID 的显式命令处理程序。 `COleDocument::OnCmdMsg` 被重写以捕获此范围内的所有命令 Id，将它们转换为从零开始的动词号，并使用) 为该谓词启动服务器 (`COleClientItem::DoVerb` 。

   不建议对此命令 ID 范围进行自定义或其他使用。

- ID_VIEW_TOOLBAR 打开和关闭工具栏

   `CFrameWnd` 处理此命令，并通过更新-命令 UI 处理程序来切换工具栏的可见状态。 工具栏必须是具有子窗口 ID AFX_IDW_TOOLBAR 的框架的子窗口。 命令处理程序实际上会切换工具栏窗口的可见性。 `CFrameWnd::RecalcLayout` 用于在工具栏处于新状态时重绘框架窗口。 当工具栏可见时，更新命令 UI 处理程序会检查菜单项。

   不建议自定义此命令处理程序。 如果要添加其他工具栏，则需要克隆和修改此命令的命令处理程序和更新-命令 UI 处理程序。

- ID_VIEW_STATUS_BAR 开启和关闭状态栏

   此命令的实现方式 `CFrameWnd` 与 ID_VIEW_TOOLBAR 一样，不同的子窗口 ID (使用 AFX_IDW_STATUS_BAR) 。

## <a name="update-only-command-handlers"></a>Update-Only 命令处理程序

在状态栏中，将使用多个标准命令 Id 作为指示器。 它们使用相同的更新-命令 UI 处理机制在应用程序空闲时显示其当前的可视状态。 由于用户无法选择它们 (也就是说，您不能将状态栏窗格推送) ，因此，对于这些命令 Id 没有 ON_COMMAND 处理程序。

- ID_INDICATOR_CAPS： CAP 锁定指示器。

- ID_INDICATOR_NUM： NUM lock 指示器。

- ID_INDICATOR_SCRL： SCRL 锁定指示器。

- ID_INDICATOR_KANA：仅适用于日语系统) 的假名锁指示器 (。

这三个在中实现 `CFrameWnd::OnUpdateKeyIndicator` ，实现帮助器使用命令 ID 映射到相应的虚拟键。 常见实现启用或禁用状态窗格 (禁用 = 不) 对象的文本， `CCmdUI` 具体取决于当前是否锁定了相应的虚拟键。

不建议自定义此命令处理程序。

- ID_INDICATOR_EXT：扩展的选择指示器。

- ID_INDICATOR_OVR：替换指示器。

- ID_INDICATOR_REC：录制指示器。

目前没有针对这些指标的标准实现。

如果选择实现这些指标，建议使用这些指示器 Id 并维护状态栏中指示器的顺序 (即，按以下顺序： EXT、CAP、NUM、SCRL、OVR、REC) 。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
