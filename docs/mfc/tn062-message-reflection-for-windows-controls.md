---
description: 了解详细信息： TN062： Windows 控件的消息反射
title: TN062：Windows 控件的消息反射
ms.date: 06/28/2018
f1_keywords:
- vc.controls.messages
helpviewer_keywords:
- ON_WM_VKEYTOITEM_REFLECT macro [MFC]
- ON_WM_DRAWITEM_REFLECT macro [MFC]
- ON_WM_VSCROLL_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT message [MFC]
- ON_CONTROL_REFLECT_EX macro [MFC]
- ON_UPDATE_COMMAND_UI_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT_EX message [MFC]
- ON_WM_HSCROLL_REFLECT macro [MFC]
- message reflection [MFC]
- ON_WM_COMPAREITEM_REFLECT macro [MFC]
- ON_WM_MEASUREITEM_REFLECT macro [MFC]
- ON_NOTIFY message [MFC]
- WM_COMMAND [MFC]
- WM_CTLCOLOR message [MFC]
- TN062 [MFC]
- ON_WM_CHARTOITEM_REFLECT macro [MFC]
- ON_WM_CTLCOLOR_REFLECT macro [MFC]
- ON_WM_DELETEITEM_REFLECT macro [MFC]
- notification messages [MFC]
- ON_WM_PARENTNOTIFY_REFLECT macro [MFC]
- WM_NOTIFY message [MFC]
- ON_CONTROL_REFLECT macro
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
ms.openlocfilehash: 9dc106c1513032e654acfc2c4b86b8eb3b939578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214723"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062：Windows 控件的消息反射

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

本技术说明介绍了消息反射，这是 MFC 4.0 中的一项新功能。 它还包含有关创建使用消息反射的简单可重复使用的控件的说明。

本技术说明不讨论消息反射，因为它适用于 (以前称为 OLE 控件) 的 ActiveX 控件。 请参阅文章 [ActiveX 控件：对 Windows 控件进行子类](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)化。

**什么是消息反射**

Windows 控件经常向其父窗口发送通知消息。 例如，许多控件都向其父级发送了控件颜色通知消息 (WM_CTLCOLOR 或) 其父项，以允许父项提供用于绘制控件背景的画笔。

在 Windows 和版本4.0 之前的 MFC 中，父窗口通常是一个对话框，负责处理这些消息。 这意味着处理消息的代码需要位于父窗口的类中，并且必须在需要处理该消息的每个类中重复。 在上面的示例中，需要具有自定义背景的控件的每个对话框都必须处理控件颜色通知消息。 如果可以编写可处理其自身背景色的控件类，则重复使用代码会容易得多。

在 MFC 4.0 中，旧机制仍可正常工作，父窗口可以处理通知消息。 此外，通过提供一种名为 "消息反射" 的功能，MFC 4.0 可方便地重用这些通知消息，可在子控件窗口或父窗口或同时在这两个窗口中进行处理。 在控件背景色示例中，现在可以通过处理反射的 WM_CTLCOLOR 消息来编写设置其自己背景色的控件类，所有这些都不依赖于父项。  (请注意，由于消息反射是由 MFC 而不是 Windows 实现的，因此必须从派生父窗口类， `CWnd` 使消息反射能够正常工作。 ) 

较早版本的 MFC 通过为一些消息提供虚函数（如 (WM_DRAWITEM 的所有者描述的列表框的消息等) ）来执行类似于消息反射的操作。 新消息反射机制是通用化且一致的。

消息反射向后兼容为4.0 之前的 MFC 版本编写的代码。

如果已为特定消息提供处理程序，或为消息范围在父窗口的类中提供了一个处理程序，则它将覆盖同一消息的反射消息处理程序，前提是您不在您自己的处理程序中调用基类处理程序函数。 例如，如果您在对话框类中处理 WM_CTLCOLOR，则您的处理将重写所有反射的消息处理程序。

如果在父窗口类中，你为特定 WM_NOTIFY 消息或 WM_NOTIFY 消息范围提供处理程序，则只有当发送这些消息的子控件没有通过反射的消息处理程序时，才会调用你的处理程序 `ON_NOTIFY_REFLECT()` 。 如果 `ON_NOTIFY_REFLECT_EX()` 在消息映射中使用，则消息处理程序可以或不允许父窗口处理该消息。 如果处理程序返回 **FALSE**，则该消息也将由父消息处理，而返回 **TRUE** 的调用不允许父代处理该消息。 请注意，将在通知消息之前处理反射的消息。

发送 WM_NOTIFY 消息时，将提供控制的第一次机会来处理该消息。 如果发送任何其他反射的消息，则父窗口有机会对其进行处理，并且控件将接收反射的消息。 为此，它需要处理程序函数和控件的类消息映射中的相应项。

反射消息的消息映射宏与常规通知的消息映射宏稍有不同：它 *_REFLECT* 追加到其常用名称。 例如，若要处理父级中的 WM_NOTIFY 消息，请在父消息映射中使用宏 ON_NOTIFY。 若要处理子控件中的反射消息，请使用子控件的消息映射中的 ON_NOTIFY_REFLECT 宏。 在某些情况下，参数也不同。 请注意，ClassWizard 通常可以为您添加消息映射项，并提供具有正确参数的主干函数实现。

有关新 WM_NOTIFY 消息的信息，请参阅 [TN061： ON_NOTIFY 和 WM_NOTIFY 消息](../mfc/tn061-on-notify-and-wm-notify-messages.md) 。

**反射消息的消息映射项和处理程序函数原型**

若要处理反射的控件通知消息，请使用下表中列出的消息映射宏和函数原型。

ClassWizard 通常可以为你添加这些消息映射项，并提供主干函数实现。 有关如何为反射消息定义处理程序的信息，请参阅为 [反射消息定义消息处理程序](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) 。

若要从消息名称转换为反射的宏名称，请在前面 *ON_* 并追加 *_REFLECT*。 例如，WM_CTLCOLOR 将变为 ON_WM_CTLCOLOR_REFLECT。  (查看可以反射哪些消息，请对下表中的宏条目执行相反的转换。 ) 

上述规则的三个例外情况如下所示：

- ON_CONTROL_REFLECT WM_COMMAND 通知的宏。

- 用于 WM_NOTIFY 反射的宏是 ON_NOTIFY_REFLECT 的。

- 用于 ON_UPDATE_COMMAND_UI 反射的宏是 ON_UPDATE_COMMAND_UI_REFLECT 的。

在上述每种特殊情况下，必须指定处理程序成员函数的名称。 在其他情况下，必须使用处理程序函数的标准名称。

函数的参数和返回值的含义记录在预置的函数名或函数 *名的下面* 。 例如， `CtlColor` 记录在中 `OnCtlColor` 。 多个反射的消息处理程序需要的参数少于父窗口中类似处理程序的参数。 只需将下表中的名称与文档中的形参名称进行匹配即可。

|映射条目|函数原型|
|---------------|------------------------|
|**ON_CONTROL_REFLECT (** `wNotifyCode`**,** `memberFxn`**)**|**afx_msg void** `memberFxn`**( ) ;**|
|**ON_NOTIFY_REFLECT (** `wNotifyCode`**,** `memberFxn`**)**|**afx_msg void** `memberFxn`**( NMHDR** <strong>\*</strong>`pNotifyStruct` **，LRESULT** <strong>\*</strong> *result* **) ;**|
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn`**)**|**afx_msg void** `memberFxn`**( CCmdUI** <strong>\*</strong>`pCmdUI` **) ;**|
|**ON_WM_CTLCOLOR_REFLECT ( )**|**AFX_MSG HBRUSH CtlColor ( CDC** <strong>\*</strong>`pDC` **，UINT** `nCtlColor` **) ;**|
|**ON_WM_DRAWITEM_REFLECT ( )**|**afx_msg Void DrawItem ( LPDRAWITEMSTRUCT** `lpDrawItemStruct`**) ;**|
|**ON_WM_MEASUREITEM_REFLECT ( )**|**afx_msg Void MeasureItem ( LPMEASUREITEMSTRUCT** `lpMeasureItemStruct`**) ;**|
|**ON_WM_DELETEITEM_REFLECT ( )**|**afx_msg Void deleteitem.php ( LPDELETEITEMSTRUCT** `lpDeleteItemStruct`**) ;**|
|**ON_WM_COMPAREITEM_REFLECT ( )**|**afx_msg Int CompareItem ( LPCOMPAREITEMSTRUCT** `lpCompareItemStruct`**) ;**|
|**ON_WM_CHARTOITEM_REFLECT ( )**|**afx_msg Int CharToItem ( UINT** `nKey`**，UINT** `nIndex`**) ;**|
|**ON_WM_VKEYTOITEM_REFLECT ( )**|**afx_msg Int VKeyToItem ( UINT** `nKey`**，UINT** `nIndex`**) ;**|
|**ON_WM_HSCROLL_REFLECT ( )**|**afx_msg Void HScroll ( UINT** `nSBCode`**，UINT** `nPos`**) ;**|
|**ON_WM_VSCROLL_REFLECT ( )**|**afx_msg Void VScroll ( UINT** `nSBCode`**，UINT** `nPos`**) ;**|
|**ON_WM_PARENTNOTIFY_REFLECT ( )**|**afx_msg Void ParentNotify ( UINT** `message`**，LPARAM** `lParam`**) ;**|

ON_NOTIFY_REFLECT 和 ON_CONTROL_REFLECT 宏具有允许多个对象 (如控件和其父) 来处理给定消息的变体。

|映射条目|函数原型|
|---------------|------------------------|
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode`**,** `memberFxn`**)**|**AFX_MSG BOOL** `memberFxn`**( NMHDR** <strong>\*</strong>`pNotifyStruct` **，LRESULT** <strong>\*</strong> *result* **) ;**|
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode`**,** `memberFxn`**)**|**AFX_MSG BOOL** `memberFxn`**( ) ;**|

## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>处理反射的消息：可重复使用的控件的示例

这个简单的示例将创建一个名为的可重用控件 `CYellowEdit` 。 控件的工作方式与常规编辑控件相同，只不过它在黄色背景上显示黑色文本。 可以轻松地添加成员函数，使 `CYellowEdit` 控件能够显示不同的颜色。

### <a name="to-try-the-example-that-creates-a-reusable-control"></a>尝试创建可重用控件的示例

1. 在现有应用程序中创建一个新对话框。 有关详细信息，请参阅 [对话框编辑器](../windows/dialog-editor.md) 主题。

   您必须有一个应用程序用于开发可重用控件。 如果没有要使用的现有应用程序，请使用应用程序向导创建一个基于对话框的应用程序。

2. 将你的项目加载到 Visual C++ 中后，使用 ClassWizard 创建一个基于的名为的新类 `CYellowEdit` `CEdit` 。

3. 将三个成员变量添加到 `CYellowEdit` 类。 前两个将是 *COLORREF* 变量来保存文本颜色和背景色。 第三个将是一个 `CBrush` 对象，该对象将包含用于绘制背景的画笔。 `CBrush`对象允许您创建一次画笔，只需在其后引用它，在控件被销毁时自动销毁画笔 `CYellowEdit` 。

4. 通过编写构造函数来初始化成员变量，如下所示：

    ```cpp
    CYellowEdit::CYellowEdit()
    {
        m_clrText = RGB(0, 0, 0);
        m_clrBkgnd = RGB(255, 255, 0);
        m_brBkgnd.CreateSolidBrush(m_clrBkgnd);
    }
    ```

5. 使用 ClassWizard，将反射 WM_CTLCOLOR 消息的处理程序添加到 `CYellowEdit` 类。 请注意，可以处理的消息列表中的消息名称前面的等号表示消息会反映出来。 为 [反射消息定义消息处理程序](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)中对此进行了说明。

   ClassWizard 为你添加了以下消息映射宏和主干函数：

    ```cpp
    ON_WM_CTLCOLOR_REFLECT()
    // Note: other code will be in between....

    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)
    {
        // TODO: Change any attributes of the DC here
        // TODO: Return a non-NULL brush if the
        //       parent's handler should not be called
        return NULL;
    }
    ```

6. 将函数主体替换为以下代码。 此代码指定文本颜色、文本背景色以及控件其余部分的背景色。

    ```cpp
    pDC->SetTextColor(m_clrText);   // text
    pDC->SetBkColor(m_clrBkgnd);    // text bkgnd
    return m_brBkgnd;               // ctl bkgnd
    ```

7. 在对话框中创建一个编辑控件，然后在按住 ctrl 键的同时双击编辑控件将其附加到成员变量。 在 "添加成员变量" 对话框中，完成变量名称并选择 "控件" 作为类别，然后选择 "CYellowEdit" 作为变量类型。 请不要忘记在对话框中设置 tab 键顺序。 此外，请确保 `CYellowEdit` 在对话框的标头文件中包含控件的标头文件。

8. 生成并运行应用程序。 编辑控件将具有黄色背景。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
