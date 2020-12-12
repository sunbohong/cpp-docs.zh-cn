---
description: 了解更多： MFC 对象之间的关系
title: MFC 对象之间的关系
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: 0646d487d1d60293461316edddcb97fde30905a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218051"
---
# <a name="relationships-among-mfc-objects"></a>MFC 对象之间的关系

为了帮助正确地对待文档/视图创建过程，请考虑正在运行的程序：文档、用于包含视图的框架窗口以及与文档关联的视图。

- 文档用于保留其视图的列表和指向创建它的文档模板的指针。

- 视图用于保留指向其文档的指针并且是其父框架窗口的子级。

- 文档框架窗口用于保留指向其当前活动视图的指针。

- 文档模板用于保留其打开的文档的列表。

- 应用程序用于保留其文档模板的列表。

- 窗口用于跟踪所有打开的窗口以便能将消息发送到这些窗口。

这些关系在文档/视图创建期间建立。 下表显示了正在运行的程序中的对象如何访问其他对象。 任何对象都可以通过调用全局函数 [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)来获取指向应用程序对象的指针。

### <a name="gaining-access-to-other-objects-in-your-application"></a>获取对应用程序中的其他对象的访问权限

|起始对象|如何访问其他对象|
|-----------------|---------------------------------|
|文档|使用 [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) 和 [GetNextView](../mfc/reference/cdocument-class.md#getnextview) 访问文档的视图列表。<br /><br /> 调用 [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) 以获取文档模板。|
|查看|调用 [GetDocument](../mfc/reference/cview-class.md#getdocument) 以获取文档。<br /><br /> 调用 [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) 以获取框架窗口。|
|文档框架窗口|调用 [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) 以获取当前视图。<br /><br /> 调用 [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) 可获取附加到当前视图的文档。|
|MDI 框架窗口|调用 [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) 以获取当前处于活动状态的 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)。|

通常，框架窗口包含一个视图，但在某些情况下（例如在拆分窗口中），同一框架窗口包含多个视图。 框架窗口保留指向当前处于活动状态的视图的指针；该指针在其他视图激活时更新。

> [!NOTE]
> 指向主框架窗口的指针存储在应用程序对象的 [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) 成员变量中。 在对的 `OnFileNew` 成员函数的重写中调用将 `InitInstance` `CWinApp` 设置 *m_pMainWnd* 。 如果您未调用 `OnFileNew`，则必须自行在 `InitInstance` 中设置变量的值。  (SDI COM 组件 (服务器) 应用程序如果在命令行上有/Embedding，则不能设置该变量。 ) 请注意， *m_pMainWnd* 现在是类的成员 `CWinThread` 而不是 `CWinApp` 。

## <a name="see-also"></a>请参阅

[文档模板和文档/视图创建过程](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[文档模板创建](../mfc/document-template-creation.md)<br/>
[文档/视图创建](../mfc/document-view-creation.md)<br/>
[创建新文档、窗口和视图](../mfc/creating-new-documents-windows-and-views.md)
