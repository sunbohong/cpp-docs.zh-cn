---
description: 了解有关以下内容的详细信息：创建 Forms-Based MFC 应用程序
title: 创建基于窗体的 MFC 应用程序
ms.date: 09/09/2019
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 2023f4f2c074ef1d0e3adf936cd4c31bd334b795
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343233"
---
# <a name="creating-a-forms-based-mfc-application"></a>创建基于窗体的 MFC 应用程序

窗体是一个对话框，其中包含允许用户访问数据并可能发生更改的控件。 你可能想要开发一个应用程序，用户可以在其中选择窗体。 通常，基于窗体的应用程序允许用户通过单击 "**文件**" 菜单中的 "**新建**" 来访问窗体。 基于对话框的应用程序不允许用户访问 "**文件**" 菜单中的 **新** 选项，也被视为基于窗体的应用程序。

单文档界面 (SDI) ，基于窗体的应用程序只允许一次运行特定窗体的一个实例。 通过从 "**文件**" 菜单中的 "**新建**" 选项中选择新的窗体，可以同时从基于 SDI 窗体的应用程序运行不同的窗体。

如果创建多文档界面 (MDI) ，基于窗体的应用程序，则该应用程序将能够支持同一窗体的多个实例。

如果创建的应用程序具有多个顶级文档支持，则桌面是文档的隐式父项，文档的框架并不限于应用程序的工作区。 可以打开文档的多个实例，每个实例都有自己的框架、菜单和任务栏图标。 可以单独关闭文档的后续实例，但如果从初始实例的 "**文件**" 菜单中选择 "**退出**" 选项，则应用程序将关闭所有实例。

SDI、MDI 和多个顶级文档应用程序都是基于窗体的，并使用文档/视图体系结构。

任何基于对话框的应用程序（按定义）都基于窗体。 基于对话框的应用程序不使用文档/视图体系结构，因此您必须为您自己的其他窗体管理创建和访问方法。

基于窗体的应用程序的基类为 [CFormView](cformview-class.md)。 如果你的应用程序具有数据库支持，则还可以选择派生自的任何类 `CFormView` 。 窗体是派生自的任何 `CFormView` 类或从继承的任何类的任何窗口 `CFormView` 。

即使使用的是基类（如 [CView](cview-class.md)），稍后也可以通过添加从派生的 [MFC 类](adding-an-mfc-class.md) ，使应用程序基于窗体 `CFormView` 。

完成向导后，你的项目将打开，如果你选择 `CFormView` (或从) 继承的类 `CFormView` 作为基类，或者如果你创建了一个基于对话框的应用程序，Visual C++ 将打开对话框编辑器。 此时，您已准备好设计您的第一个窗体。

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>开始创建基于窗体的 MFC 可执行文件

1. 按照为基于窗体的 MFC 应用程序 [创建 Mfc 应用程序](creating-an-mfc-application.md) 中的说明进行操作。

1. 在 "MFC 应用程序向导 [应用程序类型](application-type-mfc-application-wizard.md) " 页上，选中 " **文档/视图体系结构支持** " 复选框。

1. 选择 " **单个文档**"、 **多个文档** 或 **多个顶级文档**。

    > [!NOTE]
    >  默认情况下，如果选择 SDI、MDI 或多个顶级文档界面应用程序， `CView` 则会在向导的 " [生成的类](generated-classes-mfc-application-wizard.md) " 页中将其设置为应用程序视图的基类。 若要创建基于窗体的应用程序，必须选择 `CFormView` 作为应用程序的视图的基类。 请注意，向导不会为基于窗体的应用程序提供打印支持。

1. 在向导的其他页面上设置所需的任何其他项目选项。

1. 单击 " **完成** " 生成主干应用程序。

有关详细信息，请参阅：

- [派生视图类](../derived-view-classes-available-in-mfc.md)

- [文档/视图体系结构的替代项](../alternatives-to-the-document-view-architecture.md)

- [应用程序设计选择](../application-design-choices.md)

## <a name="see-also"></a>请参阅

[MFC 应用程序向导](mfc-application-wizard.md)<br/>
[窗体视图](../form-views-mfc.md)<br/>
[Explorer-Style MFC 应用程序创建文件](creating-a-file-explorer-style-mfc-application.md)<br/>
[创建 Web Browser-Style MFC 应用程序](creating-a-web-browser-style-mfc-application.md)
