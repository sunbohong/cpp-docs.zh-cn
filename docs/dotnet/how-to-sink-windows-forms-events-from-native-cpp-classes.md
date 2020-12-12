---
description: 了解有关详细信息，请参阅如何：接收来自本机 c + + 类的 Windows 窗体事件
title: 如何：接收来自本机 C++ 类的 Windows 窗体事件
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
ms.openlocfilehash: 223590849f114bfe02b030a0639f160b8fc1c321
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286353"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>如何：接收来自本机 C++ 类的 Windows 窗体事件

可以启用本机 c + + 类，从 Windows 窗体控件或其他窗体使用 MFC 宏映射格式引发的托管事件接收回调。 在视图和对话中接收事件类似于为控件执行相同的任务。

若要实现此目的，需要：

- `OnClick`使用[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)将事件处理程序附加到控件。

- 使用 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)、 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)和 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)创建委托映射。

此示例将继续执行 [如何：执行 DDX/DDV 数据绑定](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)中的工作 Windows 窗体。

现在，将 MFC 控件 (`m_MyControl`) 与 `OnClick` 为托管事件调用的托管事件处理程序委托相关联 <xref:System.Windows.Forms.Control.Click> 。

### <a name="to-attach-the-onclick-event-handler"></a>附加 OnClick 事件处理程序：

1. 将以下代码添加到 BOOL CMFC01Dlg：： OnInitDialog 的实现：

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. 将以下代码添加到 CMFC01Dlg： public CDialog 类的声明中的 public 部分。

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. 最后，将的实现添加 `OnClick` 到 CMFC01Dlg：

    ```
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)
    {
        AfxMessageBox(_T("Button clicked"));
    }
    ```

## <a name="see-also"></a>请参阅

[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)<br/>
[END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)
