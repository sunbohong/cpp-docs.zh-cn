---
description: 了解更多相关信息： MFC 中可用的派生视图类
title: MFC 中可用的派生视图类
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 669fb0f47cc2124fcf45d0eed3666869837f56f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211890"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC 中可用的派生视图类

下表显示 MFC 的视图类及其相互之间的关系。 视图类的功能取决于它所派生的 MFC 视图类。

### <a name="view-classes"></a>视图类

|类|描述|
|-----------|-----------------|
|[CView](reference/cview-class.md)|所有视图的基类。|
|[CCtrlView](reference/cctrlview-class.md)|`CTreeView`、、和的 `CListView` 基类 `CEditView` `CRichEditView` 。 通过这些类，您可以将文档/视图体系结构用于所指示的 Windows 公共控件。|
|[CEditView](reference/ceditview-class.md)|基于 Windows 编辑框控件的简单视图。 允许输入和编辑文本，并可用作简单文本编辑器应用程序的基础。 另请参阅 `CRichEditView`。|
|[CRichEditView](reference/cricheditview-class.md)|包含 [CRichEditCtrl](reference/cricheditctrl-class.md) 对象的视图。 此类类似于， `CEditView` 但不同于 `CEditView` `CRichEditView` 处理格式化文本。|
|[CListView](reference/clistview-class.md)|包含 [CListCtrl](reference/clistctrl-class.md) 对象的视图。|
|[CTreeView](reference/ctreeview-class.md)|包含 [CTreeCtrl](reference/ctreectrl-class.md) 对象的视图，适用于 Visual C++ 中的解决方案资源管理器窗口的视图。|
|[CScrollView](reference/cscrollview-class.md)|`CFormView`、和的基类 `CRecordView` `CDaoRecordView` 。 实现滚动视图的内容。|
|[CFormView](reference/cformview-class.md)|窗体视图（包含控件的视图）。 基于窗体的应用程序提供一个或多个此类窗体接口。|
|[CHtmlView](reference/chtmlview-class.md)|应用程序的用户可以浏览万维网上的站点的 Web 浏览器视图，以及本地文件系统中和网络上的文件夹。 Web 浏览器视图还可以作为活动文档容器。|
|[CRecordView](reference/crecordview-class.md)|在控件中显示 ODBC 数据库记录的窗体视图。 如果在项目中选择 "ODBC 支持"，则视图的基类为 `CRecordView` 。 视图已连接到 `CRowset` 对象。|
|[CDaoRecordView](reference/cdaorecordview-class.md)|在控件中显示 DAO 数据库记录的窗体视图。 如果在项目中选择 DAO 支持，则该视图的基类为 `CDaoRecordView` 。 视图已连接到 `CDaoRecordset` 对象。|
|[COleDBRecordView](reference/coledbrecordview-class.md)|显示控件中 OLE DB 记录的窗体视图。 如果在项目中选择 "OLE DB 支持"，则视图的基类为 `COleDBRecordView` 。 视图已连接到 `CRowset` 对象。|

> [!NOTE]
> 自 MFC 版本4.0 开始， `CEditView` 派生自 `CCtrlView` 。

若要在应用程序中使用这些类，请从应用程序中派生应用程序的视图类。 有关相关信息，请参阅 [滚动和缩放视图](scrolling-and-scaling-views.md)。 有关数据库类的详细信息，请参阅 [概述：数据库编程](../data/data-access-programming-mfc-atl.md)。

## <a name="see-also"></a>请参阅

[使用视图](using-views.md)
