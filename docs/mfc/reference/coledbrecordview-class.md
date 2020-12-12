---
description: 了解详细信息： COleDBRecordView 类
title: COleDBRecordView 类
ms.date: 11/04/2016
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
ms.openlocfilehash: bce03a482aff558ed6d22c7720ff74f304a9214f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227307"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView 类

显示控件中数据库记录的视图。

## <a name="syntax"></a>语法

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[COleDBRecordView：： COleDBRecordView](#coledbrecordview)|构造 `COleDBRecordView` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[COleDBRecordView：： OnGetRowset](#ongetrowset)|返回标准的 HRESULT 值。|
|[COleDBRecordView：： OnMove](#onmove)|更新当前记录 (如果数据源上有脏) ，然后移动到指定记录 ("下一步"、"上一步"、"上一步" 或 "最后一个") 。|

## <a name="remarks"></a>备注

视图是直接连接到对象的窗体视图 `CRowset` 。 视图是通过对话框模板资源创建的，它 `CRowset` 在对话框模板的控件中显示对象的字段。 `COleDBRecordView`对象使用对话框数据交换 (DDX) 以及内置于中的导航功能， `CRowset` 自动在窗体上的控件和行集的字段之间移动数据。 `COleDBRecordView` 还提供移动到第一条、下一条、上一条记录或最后一条记录的默认实现，以及用于更新当前视图上的记录的接口。

您可以使用的 DDX 函数 `COleDbRecordView` 直接从数据库记录集中获取数据，并将其显示在对话控件中。 应使用 (的 `DDX_*` 方法 `DDX_Text` ，如) ，而不是 `DDX_Field*` (如 `DDX_FieldText`) 的函数 `COleDbRecordView` 。 `DDX_FieldText` 不能与一起使用， `COleDbRecordView` 因为 `DDX_FieldText` `CRecordset*` `CRecordView`) 或 (的 (的其他参数用于 `CDaoRecordset*` `CDaoRecordView`) 。

> [!NOTE]
> 如果使用的是 (DAO) 类而不是 OLE DB 使用者模板类的数据访问对象，请改用类 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 。 有关详细信息，请参阅文章 [概述：数据库编程](../../data/data-access-programming-mfc-atl.md)。

`COleDBRecordView` 跟踪行集中用户的位置，以便记录视图可以更新用户界面。 当用户移到行集的任一末尾时，记录视图将禁用用户界面对象（如菜单项或工具栏按钮），以便在同一方向上进一步移动。

有关行集类的详细信息，请参阅 [Using OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md) 一文。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>要求

**标头：** afxoledb

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a> COleDBRecordView：： COleDBRecordView

构造 `COleDBRecordView` 对象。

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>parameters

*lpszTemplateName*<br/>
包含以 null 结尾的字符串，它是对话框模板资源的名称。

*nIDTemplate*<br/>
包含对话框模板资源的 ID 号。

### <a name="remarks"></a>备注

当你创建派生自的类型的对象时 `COleDBRecordView` ，将调用其中一个构造函数来创建视图对象，并确定该视图所基于的对话框资源。 可以按名称标识资源 (将字符串作为参数传递给构造函数) 或通过其 ID (传递无符号整数作为参数) 。

> [!NOTE]
> 派生类 *必须* 提供其自己的构造函数。 在构造函数中，调用构造函数， `COleDBRecordView::COleDBRecordView` 并将资源名称或 ID 作为参数。

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a> COleDBRecordView：： OnGetRowset

返回与记录视图关联的 **CRowset<>** 对象的句柄。

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

必须重写此成员函数以构造或获取行集对象，并返回该对象的句柄。 如果使用 ClassWizard 声明记录视图类，向导将为你写入默认替代。 ClassWizard 的默认实现返回存储在记录视图中的行集句柄（如果存在）。 如果不是，它将构造使用 ClassWizard 指定的类型的行集对象，并调用其 `Open` 成员函数打开表或运行查询，然后返回该对象的句柄。

> [!NOTE]
> 在 MFC 7.0 之前， `OnGetRowset` 返回指向的指针 `CRowset` 。 如果有调用的代码 `OnGetRowset` ，则需要将返回类型更改为模板化类 **CRowset<>**。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

有关详细信息和示例，请参阅 [记录视图：使用记录视图一](../../data/using-a-record-view-mfc-data-access.md)文。

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a> COleDBRecordView：： OnMove

移动到行集中的另一条记录，并在记录视图的控件中显示其字段。

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>parameters

*nIDMoveCommand*<br/>
以下标准命令 ID 值之一：

- ID_RECORD_FIRST-转到记录集中的第一条记录。

- ID_RECORD_LAST-转到记录集中的最后一条记录。

- ID_RECORD_NEXT-转到记录集中的下一条记录。

- ID_RECORD_PREV-转到记录集中的上一条记录。

### <a name="return-value"></a>返回值

如果移动成功，则为非零值;否则为0。

### <a name="remarks"></a>备注

默认实现将调用 `Move` `CRowset` 与记录视图关联的对象的相应成员函数。

默认情况下， `OnMove` 如果用户已在记录视图中更改了数据源中的记录，则将更新该记录。

应用程序向导创建一个菜单资源，其中包含第一个记录、最后一个记录、下一个记录和上一个 "记录" 菜单项。 如果选择 "可停靠工具栏" 选项，则应用程序向导还会创建一个工具栏，其中包含与这些命令对应的按钮。

如果移过记录集中的最后一条记录，记录视图将继续显示最后一条记录。 如果向后移动第一条记录，记录视图将继续显示第一条记录。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)
