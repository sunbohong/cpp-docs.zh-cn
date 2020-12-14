---
description: 了解详细信息： TN030：自定义打印和打印预览
title: TN030：自定义打印和打印预览
ms.date: 06/28/2018
f1_keywords:
- vc.print
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
ms.openlocfilehash: 6fc0571b908f85b24b8a0752a00842077d537dce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215607"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030：自定义打印和打印预览

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

此注释描述了自定义打印和打印预览的过程，并介绍了在 `CView` 和的回调例程和成员函数中使用的回调例程的用途 `CPreviewView` 。

## <a name="the-problem"></a>问题

MFC 为大多数打印和打印预览需求提供了一个完整的解决方案。 在大多数情况下，需要一些额外的代码才能使视图能够打印和预览。 不过，可以通过多种方式优化需要对开发人员进行大量工作的打印，并且某些应用程序需要将特定的用户界面元素添加到打印预览模式。

## <a name="efficient-printing"></a>高效打印

当 MFC 应用程序使用标准方法进行打印时，Windows 会将所有图形设备接口 (GDI) 对内存中图元文件的输出调用。 `EndPage`调用时，Windows 会为打印机每个要打印一页的物理带区播放一次图元文件。 在此呈现过程中，GDI 经常会查询中止过程以确定是否应该继续。 通常，abort 过程允许处理消息，以便用户可以使用打印对话框中止打印作业。

遗憾的是，这可能会降低打印过程的速度。 如果你的应用程序中的打印必须比使用标准技术实现的速度快，则必须实现手动分级。

## <a name="print-banding"></a>打印分级

若要手动带区，必须重新实现打印循环，以便每个 `OnPrint` 页面调用多次 (一次) 。 打印循环是在 viewprnt 中的函数中实现的 `OnFilePrint` 。 在 `CView` 派生类中，将重载此函数，以便用于处理打印命令的消息映射项会调用您的打印函数。 复制 `OnFilePrint` 例程并更改打印循环以实现条带。 你可能还需要将 "条带" 矩形传递到打印功能，以便可以根据要打印的页面的部分来优化绘图。

其次，在 `QueryAbort` 绘制带区时，必须经常调用。 否则，将不会调用该中止过程，并且用户将无法取消打印作业。

## <a name="print-preview-electronic-paper-with-user-interface"></a>打印预览：带有用户界面的电子纸张

打印预览本质上是尝试将显示内容转换为打印机的仿真。 默认情况下，主窗口的工作区用于在窗口内完全显示一页或两页。 用户可以放大页面的某个区域，以便更详细地查看。 有了额外支持，用户甚至可以在预览模式下编辑文档。

## <a name="customizing-print-preview"></a>自定义打印预览

此注释仅涉及修改打印预览的一个方面：将 UI 添加到预览模式。 其他修改是可能的，但此类更改不在本文讨论范围内。

## <a name="to-add-ui-to-the-preview-mode"></a>将 UI 添加到预览模式

1. 从派生视图类 `CPreviewView` 。

2. 为所需的 UI 方面添加命令处理程序。

3. 如果要向显示内容中添加视觉对象，请 `OnDraw` 在调用后重写并执行绘图 `CPreviewView::OnDraw` 。

## <a name="onfileprintpreview"></a>OnFilePrintPreview

这是 "打印预览" 的命令处理程序。 其默认实现是：

```cpp
void CView::OnFilePrintPreview()
{
    // In derived classes, implement special window handling here
    // Be sure to Unhook Frame Window close if hooked.

    // must not create this on the frame. Must outlive this function
    CPrintPreviewState* pState = new CPrintPreviewState;

    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR, this,
        RUNTIME_CLASS(CPreviewView), pState))
    {
        // In derived classes, reverse special window handling
        // here for Preview failure case

        TRACE0("Error: DoPrintPreview failed");
        AfxMessageBox(AFX_IDP_COMMAND_FAILURE);
        delete pState;  // preview failed to initialize, delete State now
    }
}
```

`DoPrintPreview` 将隐藏应用程序的主窗格。 可以通过在 pState->*dwStates* 成员中指定控件条（如状态栏）来保留它们 (这是一个位掩码，AFX_CONTROLBAR_MASK ( AFX_IDW_MYBAR # A4 定义各个控件条的位。 >pState *nIDMainPane* 窗口会自动隐藏和 reshown。 `DoPrintPreview` 然后，将为标准预览 UI 创建按钮栏。 如果需要特殊的窗口处理（如隐藏或显示其他窗口），则应在调用之前执行此操作 `DoPrintPreview` 。

默认情况下，当打印预览完成时，它会将控件条返回到其原始状态，并使主窗格可见。 如果需要特殊处理，则应在重写中完成此操作 `EndPrintPreview` 。 如果 `DoPrintPreview` 失败，还提供特殊处理。

通过以下方式调用 DoPrintPreview：

- 预览工具栏的对话框模板的资源 ID。

- 指向用于执行打印预览打印的视图的指针。

- 预览视图类的运行时类。 这将在 DoPrintPreview 中动态创建。

- CPrintPreviewState 指针。 请注意，如果应用程序需要保留更多状态，则 CPrintPreviewState 结构 (或派生结构 *) 不得在* 该帧上创建。 DoPrintPreview 是无模式的，在调用 EndPrintPreview 之前，此结构必须仍然存在。

  > [!NOTE]
  > 如果打印支持需要单独的视图或视图类，则指向该对象的指针应作为第二个参数传递。

## <a name="endprintpreview"></a>EndPrintPreview

这称为终止打印预览模式。 通常需要移动到上次在 "打印预览" 中显示的文档中的页面。 `EndPrintPreview` 是应用程序的机会。 >pInfo *m_nCurPage* 成员是指如果两个页面都显示) ，则最后显示的页面 (最左端，而指针是有关用户感兴趣的页面上位置的提示。 由于应用程序的视图结构对于框架是未知的，因此您必须提供代码以移动到所选点。

在调用之前，应执行大多数操作 `CView::EndPrintPreview` 。 此调用会反转的效果， `DoPrintPreview` 并删除 pView、pDC 和 pInfo。

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp：： OnFilePrintSetup

必须为 "打印设置" 菜单项映射此项。 在大多数情况下，不需要重写实现。

## <a name="page-nomenclature"></a>页命名法

另一个问题是页码和顺序的问题。 对于简单的字处理器类型应用程序，这是一个简单的问题。 大多数打印预览系统都假设每个打印页面都对应于文档中的一页。

尝试提供通用化解决方案时，需要考虑几个事项。 假设 CAD 系统。 用户有一个绘图，其中包含几个电子大小的工作表。 在电子尺寸 (或更小、缩放) 绘图仪上，在简单的情况下页码就会相同。 但在激光打印机上，每张纸打印16个大小的页面，打印预览会认为 "页面"

作为简介段落状态，打印预览的作用类似于打印机。 因此，用户将看到所选特定打印机的内容。 它由视图确定每个页面上打印的图像。

结构中的页说明字符串 `CPrintInfo` 提供了一种方法，用于向用户显示页码（如果该页码可以表示为每页一个数字） (如 "page 1" 或 "Pages 1-2" ) 。 此字符串由的默认实现使用 `CPreviewView::OnDisplayPageNumber` 。 如果需要不同的显示，则可以重写此虚函数以提供，例如，"Sheet1，Sections A，B"。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
