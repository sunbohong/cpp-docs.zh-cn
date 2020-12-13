---
description: 了解详细信息：使用 OLE DB 记录视图
title: 使用 OLE DB 记录视图
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
ms.openlocfilehash: 8230ba118038852f81159d21a51165b7448a26aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332459"
---
# <a name="using-ole-db-record-views"></a>使用 OLE DB 记录视图

如果要在 MFC 应用程序中显示 OLE DB 行集数据，请使用 MFC 类 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)。 通过创建的记录视图对象， `COleDBRecordView` 您可以在 MFC 控件中显示数据库记录。 记录视图是直接连接到从模板类创建的 OLE DB 行集对象的对话框窗体视图 `CRowset` 。 获取行集对象的句柄非常简单：

```cpp
COleDBRecordView myRecordView;
...
// CProductAccessor is a user record class
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();
```

视图在 `CRowset` 对话框的控件中显示对象的字段。 `COleDBRecordView`对象使用对话框数据交换 (DDX) 以及内置 `CRowset` `MoveFirst` 于 (、、和) 中的导航功能， `MoveNext` `MovePrev` `MoveLast` 自动在窗体上的控件和行集的字段之间移动数据。 `COleDBRecordView` 跟踪行集中的用户位置，以便记录视图可以更新用户界面，并提供 [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) 方法以便在移动到另一记录之前更新当前记录。

您可以使用的 DDX 函数 `COleDbRecordView` 直接从数据库记录集中获取数据，并将其显示在对话控件中。 使用 **DDX_** <strong>\*</strong> 方法 (例如 `DDX_Text`) ，而不是 **DDX_Field** <strong>\*</strong> 函数 (例如 `DDX_FieldText` 使用) `COleDbRecordView` 。

## <a name="see-also"></a>请参阅

[使用访问器](../../data/oledb/using-accessors.md)<br/>
[COleDBRecordView 类](../../mfc/reference/coledbrecordview-class.md)<br/>
