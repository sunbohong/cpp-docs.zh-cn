---
description: 了解详细信息： TN029：拆分窗口
title: TN029：拆分窗口
ms.date: 11/04/2016
f1_keywords:
- vc.windows.splitter
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
ms.openlocfilehash: e1079adf403b64aa47f5aae00aa32f7da702ddcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215633"
---
# <a name="tn029-splitter-windows"></a>TN029：拆分窗口

此注释描述 MFC [CSplitterWnd 类，该类](../mfc/reference/csplitterwnd-class.md)提供窗口拆分，并管理其他窗格窗口的大小调整。

## <a name="splitter-styles"></a>拆分器样式

`CSplitterWnd`支持两种不同的拆分窗口样式。

在 "静态拆分器" 中，拆分窗口在创建时创建窗格。 窗格的顺序和数量永远不会改变。 拆分条用于调整不同窗格的大小。 您可以使用此样式在每个窗格中显示不同的视图类。 Visual C++ 图形编辑器和 Windows 文件管理器是使用此拆分器样式的程序示例。 这种拆分窗口样式不使用拆分框。

在 "动态拆分器" 中，创建并销毁其他窗格，因为用户拆分和取消拆分新视图。 此拆分器从单个视图开始，并为用户提供拆分器框以启动拆分。 当视图在一个方向上拆分时，拆分窗口会动态创建一个新的视图对象。 此新视图对象表示新窗格。 如果通过使用键盘界面以两个方向拆分视图，则拆分窗口将为三个新窗格创建三个新视图对象。 拆分处于活动状态时，Windows 会将拆分框显示为窗格之间的拆分栏。 当用户取消拆分时，Windows 会销毁其他视图对象，但原始视图将保留，直到拆分器窗口本身被销毁。 Microsoft Excel 和 Microsoft Word 是使用动态拆分器样式的应用程序的示例。

创建这两种拆分窗口时，必须指定拆分器将管理的最大行数和列数。 静态拆分器将创建窗格以填充所有行和列。 创建时，动态拆分器将仅创建第一个窗格 `CSplitterWnd` 。

可以为静态拆分器指定的最大窗格数为16行（16列）。 建议的配置包括：

- 1行 x 2 列：通常具有不同的窗格

- 2行 x 1 列：通常包含不同的窗格

- 2行 x 2 列：通常具有相似的窗格

可为动态拆分器指定的窗格的最大数目为2行（2列）。 建议的配置包括：

- 1行 x 2 列：对于纵栏数据

- 2行 x 1 列：用于文本或其他数据

- 2行 x 2 列：适用于网格或面向表的数据

## <a name="splitter-examples"></a>拆分器示例

许多 MFC 示例程序直接或间接使用拆分器窗口。 MFC 常规示例 [VIEWEX](../overview/visual-cpp-samples.md) 阐释了静态拆分器的几个用途，包括如何在拆分器中放置拆分器。

还可以使用 ClassWizard 创建新的多文档界面 (MDI) 包含拆分器窗口的子框架窗口类。 有关拆分窗口的详细信息，请参阅 [多文档类型、视图和框架窗口](../mfc/multiple-document-types-views-and-frame-windows.md)。

## <a name="terminology-used-by-implementation"></a>实现所使用的术语

下面列出了特定于拆分窗口的术语：

`CSplitterWnd`：提供窗格拆分控件和滚动条的窗口，这些控件和滚动条在行或列上的所有窗格之间共享。 指定包含从零开始的数字的行和列 (第一个窗格的行 = 0，列 = 0) 。

窗格：管理的应用程序特定的窗口 `CSplitterWnd` 。 窗格通常是派生自 [CView 类](../mfc/reference/cview-class.md)的对象，但可以是具有相应子窗口 ID 的任意 [CWnd](../mfc/reference/cwnd-class.md) 对象。

若要使用 `CWnd` 派生的对象，请将对象的 RUNTIME_CLASS 传递到函数，就 `CreateView` 像使用派生类的情况一样 `CView` 。 类必须使用 DECLARE_DYNCREATE 和 IMPLEMENT_DYNCREATE，因为框架在运行时使用动态创建。 尽管中有很多 `CSplitterWnd` 特定于类的代码，但在 `CView` 执行这些操作之前，将始终使用 [CObject：： IsKindOf](../mfc/reference/cobject-class.md#iskindof) 。

拆分栏：放置在窗格的行和列之间的控件。 它可用于调整窗格的行或列的大小。

拆分框：动态中 `CSplitterWnd` 可用于创建窗格的新行或列的控件。 它位于垂直滚动条的顶部或水平滚动条的左侧。

拆分器交集：垂直拆分条和水平拆分条的交集。 可以拖动它来同时调整行和窗格的列的大小。

## <a name="shared-scroll-bars"></a>共享的滚动条

`CSplitterWnd`类还支持共享的滚动条。 这些滚动条控件是的子控件 `CSplitterWnd` ，并与拆分器中的不同窗格共享。

例如，在1行 x 2 列窗口中，您可以在创建时指定 WS_VSCROLL `CSplitterWnd` 。 Windows 将创建一个在两个窗格之间共享的特殊滚动条控件。

```
[      ][      ][^]
[pane00][pane01][|]
[      ][      ][v]
```

当用户移动滚动条时，WM_VSCROLL 的消息将发送到这两个视图。 当任一视图设置滚动条的位置时，将设置共享滚动条。

请注意，共享滚动条对于类似的视图对象最为有用。 如果在拆分器中混合了不同类型的视图，则可能需要编写特殊代码来协调滚动位置。 `CView`使用滚动条 api 的任何派生类 `CWnd` 都将委托给共享的滚动条（如果存在）。 `CScrollView`实现是 `CView` 支持共享滚动条的类的一个示例。 不是派生自的类 `CView` 、依赖于非控件滚动条的类或使用标准 Windows 实现的类 (例如， `CEditView`) 不能与的共享滚动条功能一起使用 `CSplitterWnd` 。

## <a name="minimum-sizes"></a>最小大小

每行都有最小行高，每列都有最小列宽。 这一最低保证窗格不太小，无法完整地显示。

对于静态拆分窗口，初始的最小行高和列宽为0。 对于动态拆分窗口，初始的最小行高和列宽由函数的 *sizeMin* 参数设置 `CSplitterWnd::Create` 。

可以使用 [CSplitterWnd：： SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) 和 [CSplitterWnd：： SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) 函数更改这些最小大小。

## <a name="actual-vs-ideal-sizes"></a>实际大小与理想大小

拆分窗口中窗格的布局取决于包含它们的帧的大小。 当用户调整包含框架的大小时，将重新 `CSplitterWnd` 定位并调整窗格的大小，使其尽可能适应。

用户可以手动设置行高和列宽大小，也可以通过使用类来设置理想大小 `CSplitterWnd` 。 实际大小可能比理想值小或大。 如果没有足够的空间来显示理想大小，或者拆分窗口的右侧或底部有太多空白空间，则 Windows 将调整实际大小。

## <a name="custom-controls"></a>自定义控件

您可以重写许多函数以提供自定义行为和自定义接口。 您可以重写此第一组，以便为拆分器窗口的各种图形组件提供备用图像。

- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`

- `virtual void OnInvertTracker(const CRect& rect);`

调用此函数可创建共享的滚动条控件。 您可以重写它，以创建滚动条旁边的额外控件。

- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`

这些函数实现动态拆分窗口的逻辑。 你可以重写这些参数以提供更高级的拆分器逻辑。

- `virtual void DeleteView(int row, int col);`

- `virtual BOOL SplitRow(int cyBefore);`

- `virtual BOOL SplitColumn(int cxBefore);`

- `virtual void DeleteRow(int rowDelete);`

- `virtual void DeleteColumn(int colDelete);`

## <a name="cview-functionality"></a>CView 功能

`CView`类使用以下高级命令委托到 `CSplitterWnd` 实现。 由于这些命令是虚拟的，因此标准 `CView` 实现不需要 `CSplitterWnd` 在中链接整个实现。 对于使用 `CView` 但不是的应用程序 `CSplitterWnd` ， `CSplitterWnd` 实现将不与应用程序关联。

- `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`

   检查当前是否可能 ID_NEXT_PANE 或 ID_PREV_PANE。

- `virtual void ActivateNext(BOOL bPrev = FALSE);`

   执行 "下一窗格" 或 "上一窗格" 命令。

- `virtual BOOL DoKeyboardSplit();`

   执行键盘拆分命令，通常为 "窗口拆分"。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
