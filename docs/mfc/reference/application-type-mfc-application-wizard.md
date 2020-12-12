---
description: 了解更多：应用程序类型，MFC 应用程序向导
title: MFC 应用程序向导的应用程序类型
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.apptype
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
ms.openlocfilehash: 178e9c1319b17e356273fc3e59d2133c8d4aa54c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322780"
---
# <a name="application-type-mfc-application-wizard"></a>MFC 应用程序向导的应用程序类型

使用 [MFC 应用程序向导](../../mfc/reference/mfc-application-wizard.md) 的此页可以设计基本功能并将其添加到新的 MFC 应用程序中。

- **应用程序类型**

  指定要在应用程序中创建的文档支持的类型。 所选应用程序的类型将决定可用于应用程序的用户界面选项。 有关详细信息，请参阅 [MFC 应用程序向导的用户界面功能](../../mfc/reference/user-interface-features-mfc-application-wizard.md) 。

   有关文档类型的详细信息，请参阅：

  - [SDI 和 MDI](../../mfc/sdi-and-mdi.md)

  - [框架窗口](../../mfc/frame-windows.md)

  - [框架窗口类](../../mfc/frame-window-classes.md)

  - [文档、视图和框架](../../mfc/documents-views-and-the-framework.md)

  - [对话框](../../mfc/dialog-boxes.md)

  |选项|描述|
  |------------|-----------------|
  |**单个文档**|为应用程序 (SDI) 体系结构创建单个文档界面，其中视图类基于 [CView 类](../../mfc/reference/cview-class.md)。 您可以在向导的 " [MFC 应用程序向导](../../mfc/reference/generated-classes-mfc-application-wizard.md) " 页的 "生成的类" 中更改视图的基类。 例如，若要创建基于窗体的应用程序，请对视图类使用 [CFormView 类](../../mfc/reference/cformview-class.md) 。<br /><br /> 在这种类型的应用程序中，文档的框架窗口只能保存一个文档。|
  |**多个文档**|为应用程序 (MDI) 体系结构创建多个文档接口，视图类基于该结构 `CView` 。 您可以在向导的 " **生成的类** " 页中更改视图的基类。 例如，若要创建基于窗体的应用程序，请对 `CFormView` 视图类使用。<br /><br /> 在这种类型的应用程序中，文档的框架窗口可以容纳多个子窗口。|
  |**选项卡式文档**|将每个文档放置在单独的选项卡上。|
  |**基于对话框**|为应用程序创建一个基于对话框的架构，其中的对话框类基于该结构 `CDialog` 。  (若要创建 HTML 对话框，请选择 " **使用 html 对话**" 框。 ) |
  |**使用 HTML 对话框**|仅适用于对话框应用程序。 从 [CDHtmlDialog 类](../../mfc/reference/cdhtmldialog-class.md) 而不是 [CDialog 类](../../mfc/reference/cdialog-class.md)派生对话框类。 如果选中此框， `CDHtmlDialog` 则将在向导的 "[生成的类" "MFC 应用程序向导](../../mfc/reference/generated-classes-mfc-application-wizard.md)" 页的 "**基类**" 框中列出。<br /><br /> `CDHtmlDialog`"派生的" 对话框显示基于 html 的对话框，将数据与 html 控件交换并处理 html 事件。|
  |**多个顶级文档**|为应用程序创建多个顶级体系结构，其中，视图类基于 `CView` 。<br /><br /> 在这种类型的应用程序中，当用户在 "**文件**" 菜单上单击 "**新建** (" 或 "**新帧**) " 时，应用程序将创建一个其父项隐式桌面的窗口。 新文档框架显示在任务栏中，并不局限于应用程序窗口的工作区。|

- **文档/视图体系结构支持**

  指定是否在应用程序中包含文档/视图体系结构，方法是使用 [CDocument 类](../../mfc/reference/cdocument-class.md) ，并使用 [CView 类](../../mfc/reference/cview-class.md) (默认) 。 如果要移植非 MFC 应用程序，或者要减小编译的可执行文件的大小，则清除此复选框。 默认情况下，没有文档/视图体系结构的应用程序派生自 [CWinApp 类](../../mfc/reference/cwinapp-class.md)，并且不包含用于从磁盘文件中打开文档的 MFC 支持。

- **资源语言**

  设置资源的语言。 此列表显示 Visual Studio 安装的系统上的可用语言。 如果要选择系统语言以外的其他语言，则必须已安装该语言的相应模板文件夹。

  您选择的语言将反映在向导的 "[文档模板字符串，MFC 应用程序向导](../../mfc/reference/document-template-strings-mfc-application-wizard.md)" 页的 "**本地化字符串**" 选项中。

- **使用 Unicode 库**

  指定是否使用 MFC 库的 Unicode 或非 Unicode 版本。

- **项目样式**

  指示应用程序是否具有标准 MFC、文件资源管理器、Visual Studio 或 Office 体系结构和显示。 有关详细信息，请参阅 [Explorer-Style MFC 应用程序创建文件](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)。

  |选项|描述|
  |------------|-----------------|
  |**MFC 标准**|提供标准 MFC 应用程序体系结构。|
  |**文件资源管理器**|使用拆分窗口实现类似文件资源管理器的应用程序，其中左窗格是 [CTreeView 类](../../mfc/reference/ctreeview-class.md) ，右窗格是 [CListView 类](../../mfc/reference/clistview-class.md)。|
  |**Visual Studio**|实现一个类似于 Visual Studio 的应用程序，其中包含四个可停靠的窗格 (**文件视图**、 **类视图**、 **属性** 和 **输出**) 派生自 [CDockablePane 类](../../mfc/reference/cdockablepane-class.md) ，以及从 [CMDIFrameWndEx 类](../../mfc/reference/cmdiframewndex-class.md) 派生的主框架窗口 (默认的) 。|
  |**Office**|实现一个类似于 Office 的应用程序，该应用程序包含从 [CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)派生的功能区、从 [CMFCOutlookBar 类](../../mfc/reference/cmfcoutlookbar-class.md)派生的 Outlook 栏、从 [CMFCCaptionBar 类](../../mfc/reference/cmfccaptionbar-class.md)派生的标题栏和派生自 [CMDIFrameWndEx 类](../../mfc/reference/cmdiframewndex-class.md)的主帧。|

- **视觉样式和颜色**

  确定应用程序的视觉样式。 可以使用以下选项：

  - **Windows Native/Default**

  - **Office 2003**

  - **Visual Studio 2005**

  - **Office 2007 (蓝色主题)**

  - **Office 2007 (黑色主题)**

  - **Office 2007 (银主题)**

  - **Office 2007 (浅绿主题)**

- **启用视觉样式切换**

  指定用户是否可以在运行时更改应用程序的视觉样式，通常通过从菜单或功能区中选择相应的视觉样式来更改。

- **MFC 的使用**

  指定如何链接到 MFC 库。 默认情况下，MFC 链接为共享 DLL。

  |选项|描述|
  |------------|-----------------|
  |**在共享 DLL 中使用 MFC**|将 MFC 库作为共享 DLL 链接到应用程序。 应用程序会在运行时调用 MFC 库。 此选项减少了包含使用 MFC 库的多个可执行文件的应用程序的磁盘和内存要求。 Win32 应用程序和 MFC 应用程序都可以调用 DLL 中的函数 (默认值) |
  |**在静态库中使用 MFC**|生成时将应用程序链接到静态 MFC 库。|

## <a name="see-also"></a>请参阅

[MFC 应用程序向导](../../mfc/reference/mfc-application-wizard.md)<br/>
[为 Visual Studio C++ 项目创建的文件类型](../../build/reference/file-types-created-for-visual-cpp-projects.md)
