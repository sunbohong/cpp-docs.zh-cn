---
description: 了解详细信息：用于创建数据库应用程序的操作顺序
title: 用于创建数据库应用程序的操作顺序
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: 86f06ae5200fc8646ccb80bfec4e2814b94f9225
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217583"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>用于创建数据库应用程序的操作顺序

下表显示了在编写数据库应用程序时角色和框架的角色。

> [!NOTE]
> 尽管包含 DAO 类，但仍可以) 使用 dao 类，但 Visual C++ 环境和向导不支持 DAO (。 Microsoft 建议对新的 MFC 项目使用 ODBC。 只应在维护现有应用程序时使用 DAO。

### <a name="creating-database-applications"></a>创建数据库应用程序

|任务|您执行的操作|框架执行的操作|
|----------|------------|------------------------|
|决定是使用 MFC ODBC 还是 DAO 类。|为新的 MFC 项目使用 ODBC。 仅使用 DAO 来维护现有应用程序。 有关一般信息，请参阅 [数据访问编程](../data/data-access-programming-mfc-atl.md)这篇文章。|框架提供支持数据库访问的类。|
|用数据库选项创建框架应用程序。|运行 MFC 应用程序向导。 在数据库支持页上选择选项。 如果选择创建记录视图的选项，还需要指定：<br /><br />-数据源和表名称或名称<br />-查询名称。|MFC 应用程序向导创建文件并指定必要的包含。 根据指定的选项，这些文件可以包含记录集类。|
|设计数据库窗体或窗体。|使用 Visual C++ 对话框编辑器将控件放置在记录视图类的对话框模板资源上。|MFC 应用程序向导创建一个空的对话框模板资源，以便您填写。|
|根据需要创建其他记录视图和记录集类。|使用类视图创建类，使用对话框编辑器设计视图。|类视图为新类创建其他文件。|
|根据需要在代码中创建记录集对象。 使用每个记录集来操作记录 .。。|记录集基于从 [CRecordset](../mfc/reference/crecordset-class.md) 派生的类和向导。|ODBC 使用记录字段交换 (RFX) 在数据库和记录集的字段数据成员之间交换数据。 如果使用记录视图，对话框数据交换 (DDX) 在记录视图的记录集和控件之间交换数据。|
|...也可以在代码中为要打开的每个数据库创建一个显式的 [CDatabase](../mfc/reference/cdatabase-class.md) 。|将记录集对象基于数据库对象。|数据库对象提供数据源的接口。|
|将数据列动态绑定到记录集。|在 ODBC 中，向派生记录集类添加代码以管理绑定。 请参阅文章 [记录集：动态绑定数据列 (ODBC) ](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)。||

## <a name="see-also"></a>请参阅

[基于框架生成](../mfc/building-on-the-framework.md)<br/>
[用于生成 MFC 应用程序的操作序列](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[用于创建 OLE 应用程序的操作顺序](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[用于创建 ActiveX 控件的操作顺序](../mfc/sequence-of-operations-for-creating-activex-controls.md)
