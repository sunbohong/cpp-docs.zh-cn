---
description: '了解详细信息：窗体视图 (MFC) '
title: 窗体视图 (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
ms.openlocfilehash: be0853c46509e92d758b38e6a3b7fbd993e9b700
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180354"
---
# <a name="form-views-mfc"></a>窗体视图 (MFC)

您可以向支持 MFC 库的任何 Visual C++ 应用程序添加窗体，包括 [基于窗体的应用程序](reference/creating-a-forms-based-mfc-application.md) (其中的视图类派生自 `CFormView`) 。 如果你最初没有创建支持窗体的应用程序，则在插入新窗体时，Visual C++ 会为你添加此支持。 在实现默认 [文档/视图体系结构](document-view-architecture.md)的 SDI 或 MDI 应用程序中，当用户默认选择 **新** 命令时 (，默认情况下，在 " **文件** " 菜单) 上，Visual C++ 提示用户从可用窗体中进行选择。

使用 SDI 应用程序时，如果未找到窗体的当前实例，则窗体的当前实例将继续运行，但会创建具有选定窗体的应用程序的新实例。 在 MDI 应用程序中，当用户选择 **新** 命令时，窗体的当前实例将继续运行。

> [!NOTE]
> 可以将窗体插入到基于对话框的应用程序中， (其对话框类基于该应用程序 `CDialog` ，而在其中没有任何视图类实现) 。 但是，如果没有文档/视图体系结构，Visual C++ 不会自动实现&#124;**新** 功能的 **文件**。 您必须为用户创建一种方法来查看其他窗体，例如通过使用各种属性页实现选项卡式对话框。

在应用程序中插入新的窗体时，Visual C++ 执行以下操作：

- 基于您选择的一种窗体样式类创建类 (`CFormView` 、 `CRecordView` 、 `CDaoRecordView` 或 `CDialog`) 。

-  (创建具有适当样式的对话框资源，或者可以使用尚未与类) 关联的现有对话框资源。

   如果选择现有的对话框资源，则可能需要通过使用对话框的 "属性" 页来设置这些样式。 对话框样式必须包括：

     **WS_CHILD**= On

     **WS_BORDER**= Off

     **WS_VISIBLE**= Off

     **WS_CAPTION**= Off

对于基于文档/视图体系结构的应用程序， **新的窗体** 命令 (右键单击类视图) ：

- 创建 `CDocument` 基于的类

   您可以 `CDocument` 在项目中使用任何基于现有的类，而不是创建新类。

- 生成一个文档模板，该模板 (派生自 `CDocument` 包含 string、menu 和 icon 资源的) 。

   你还可以创建一个新类，以便在其基础上创建模板。

- `AddDocumentTemplate`在应用程序的代码中添加对的调用 `InitInstance` 。

   Visual C++ 会为你创建的每个新表单添加此代码，这将在用户选择 **新** 命令时将表单添加到可用表单列表。 此代码包括窗体的关联资源 ID 以及关联的文档、视图和框架类的名称，共同构成新的窗体对象。

   文档模板用作文档、框架窗口和视图之间的连接。 对于单个文档，可以创建多个模板。

有关详细信息，请参阅：

- [创建 Forms-Based 应用程序](reference/creating-a-forms-based-mfc-application.md)

- [在项目中插入窗体](inserting-a-form-into-a-project.md)

## <a name="see-also"></a>请参阅

[用户界面元素](user-interface-elements-mfc.md)
