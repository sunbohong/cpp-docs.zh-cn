---
description: 了解详细信息： CCreateContext 结构
title: CCreateContext 结构
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: b0d8c3a38d4d6ce9ee6130092ea6b27a50ed15e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220456"
---
# <a name="ccreatecontext-structure"></a>CCreateContext 结构

框架 `CCreateContext` 在创建与文档相关联的框架窗口和视图时使用结构。

## <a name="syntax"></a>语法

```
struct CCreateContext
```

## <a name="remarks"></a>备注

`CCreateContext` 为结构，并且不具有基类。

创建窗口时，此结构中的值将提供用于将文档的组件连接到其数据的视图的信息。 仅 `CCreateContext` 当要重写创建过程的一部分时，才需要使用。

`CCreateContext`结构包含指向文档、框架窗口、视图和文档模板的指针。 它还包含指向的指针 `CRuntimeClass` ，该指针标识要创建的视图的类型。 运行时类信息和当前文档指针用于动态创建新视图。 下表说明了如何和何时使用每个 `CCreateContext` 成员：

|成员|类型|它的用途|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` 要创建的新视图的。|
|`m_pCurrentDoc`|`CDocument*`|要与新视图关联的现有文档。|
|`m_pNewDocTemplate`|`CDocTemplate*`|与创建新的 MDI 框架窗口关联的文档模板。|
|`m_pLastView`|`CView*`|对附加视图建模的原始视图，如创建拆分器窗口视图或在文档中创建第二个视图时。|
|`m_pCurrentFrame`|`CFrameWnd*`|在其中对其他框架窗口进行建模的框架窗口，就像在文档中创建第二个框架窗口时。|

当文档模板创建文档及其关联组件时，它将验证结构中存储的信息 `CCreateContext` 。 例如，不应为不存在的文档创建视图。

> [!NOTE]
> 中的所有指针 `CCreateContext` 均为可选， `NULL` 如果未指定或未知，则可以为。

`CCreateContext` 由 "另请参阅" 下列出的成员函数使用。 如果打算重写这些函数的说明，请参考这些功能的说明。

下面是几个通用指导原则：

- 当作为的参数（如、和）传递时 `CWnd::Create` ， `CFrameWnd::Create` `CFrameWnd::LoadFrame` create 上下文指定新窗口应连接到的内容。 对于大多数窗口，整个结构是可选的， `NULL` 可以传递指针。

- 对于可重写的成员函数（如 `CFrameWnd::OnCreateClient` ）， `CCreateContext` 参数是可选的。

- 对于视图创建中涉及的成员函数，您必须提供足够的信息来创建视图。 例如，对于拆分窗口中的第一个视图，您必须提供视图类信息和当前文档。

通常，如果使用框架默认值，可以忽略 `CCreateContext` 。 如果尝试进行更高级的修改，则 Microsoft 基础类库的源代码或示例程序（如 VIEWEX）将引导您。 如果忘记了必需的参数，框架断言会告诉您忘记的内容。

有关的详细信息 `CCreateContext` ，请参阅 MFC 示例 [VIEWEX](../../overview/visual-cpp-samples.md)。

## <a name="requirements"></a>要求

**标头：** afxext。h

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd：： Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd：： LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd：： OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd：： Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd：： CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)
