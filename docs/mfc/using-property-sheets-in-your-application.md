---
title: 在您的应用程序中使用属性表
ms.date: 11/04/2016
helpviewer_keywords:
- dialog templates [MFC], property sheets
- dialog resources
- property pages [MFC], property sheets
- DoModal method property sheets
- AddPage method [MFC]
- property sheets, about property sheets
- Create method [MFC], property sheets
- CPropertyPage class [MFC], styles
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
ms.openlocfilehash: 789764c9af988135219bd710d4f8aec1cda9143a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504645"
---
# <a name="using-property-sheets-in-your-application"></a>在您的应用程序中使用属性表

若要在应用程序中使用属性表，请完成下列步骤：

1. 为每个属性页创建对话框模板资源。 记住，用户可能从一页切换到另一页，因此，尽量让每页的布局一致。

   所有页的对话框模板的大小不必相同。 框架将使用最大页的大小确定要在属性页的属性表中分配的空间。

   当您为属性页创建对话框模板资源时，您必须在“对话框属性”属性表中指定下列样式：

   - 将 "**常规**" 页上的 "**标题**" 编辑框设置为要在此页的选项卡中显示的文本。

   - 将 "**样式**" 页上的 "**样式**" 列表框设置为 "**子级**"。

   - 将 "**样式**" 页上的 "**边框**" 列表框设置为 "**细**"。

   - 确保已选中 "**样式**" 页上的 "**标题栏**" 复选框。

   - 确保已选中 "**更多样式**" 页上的 "**已禁用**" 复选框。

1. 创建对应于每个属性页对话框模板的 [CPropertyPage](../mfc/reference/cpropertypage-class.md)派生类。 请参阅 [添加类](../ide/adding-a-class-visual-cpp.md)。 请选择 `CPropertyPage` 作为基类。

1. 创建成员变量以保存此属性页的值。 将成员变量添加到属性页的过程与将成员变量添加到对话框的过程完全一致，因为属性页是一个特殊化对话框。 有关详细信息，请参阅 [定义对话框控件的成员变量](../windows/adding-editing-or-deleting-controls.md)。

1. 在源代码中构造 [CPropertySheet](../mfc/reference/cpropertysheet-class.md) 对象。 通常，您将在显示属性表的命令的处理程序中构造 `CPropertySheet` 对象。 此对象表示整个属性表。 如果使用 [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) 函数创建了模式属性表，则默认情况下，框架将提供三个命令按钮： "确定"、"取消" 和 "应用"。 对于用 [Create](../mfc/reference/cpropertysheet-class.md#create) 函数创建的无模式属性表，框架不创建任何命令按钮。 您无需从 `CPropertySheet` 派生类，除非希望添加其他控件（如预览窗口）或显示无模式属性表。 此步骤对于无模式属性表是必需的，因为它们可能不包含可能用于关闭属性表的任何默认控件。

1. 对于将添加到属性表的每个页，请执行下列操作：

   - 为在此过程前面创建的每个 `CPropertyPage` 派生类构造一个对象。

   - 为每一页调用 [CPropertySheet：： AddPage](../mfc/reference/cpropertysheet-class.md#addpage) 。

   通常，创建 `CPropertySheet` 的对象在该步骤中还将创建 `CPropertyPage` 对象。 但是，如果实现 `CPropertySheet` 派生类，则可将 `CPropertyPage` 对象嵌入 `CPropertySheet` 对象并从 `AddPage` 派生类构造函数为每页调用 `CPropertySheet`。 `AddPage` 会将 `CPropertyPage` 对象添加到属性表的页列表，但不会实际为该页创建窗口。 因此，无需等到创建属性表窗口后再调用 `AddPage`；您可通过属性表的构造函数调用 `AddPage`。

   默认情况下，如果属性表具有的选项卡在属性表的单个行中放不下，这些选项卡则会堆叠在多个行中。 若要禁用堆栈，请调用 [CPropertySheet：： EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) ，并将参数设置为 **FALSE**。 您必须在创建属性表时调用 `EnableStackedTabs`。

1. 调用 [CPropertySheet：:D omodal](../mfc/reference/cpropertysheet-class.md#domodal) 或 [Create](../mfc/reference/cpropertysheet-class.md#create) 以显示属性表。 调用 `DoModal` 以将属性表作为模式对话框创建。 调用 **create** 以创建属性表作为无模式对话框。

1. 在属性页和属性表的所有者之间交换数据。 [交换数据](../mfc/exchanging-data.md)一文中对此进行了说明。

有关如何使用属性表的示例，请参阅 MFC 常规示例 [PROPDLG](../overview/visual-cpp-samples.md)。

## <a name="see-also"></a>请参阅

[属性表](../mfc/property-sheets-mfc.md)
