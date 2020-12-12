---
description: 了解有关详细信息，请参阅如何：调用 Windows 窗体控件的属性和方法
title: 如何：调用 Windows 窗体控件的属性和方法
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
ms.openlocfilehash: a797084a28eefec27699814a09c8521da7460bc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268400"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>如何：调用 Windows 窗体控件的属性和方法

因为 [CWinFormsView：： GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) 返回指向的指针 <xref:System.Windows.Forms.Control?displayProperty=fullName> ，而不是指向的指针，所以 `WindowsControlLibrary1::UserControl1` 建议添加 user 控件类型的成员，并在 [IView：： OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate)中对其进行初始化。 现在，你可以使用调用方法和属性 `m_ViewControl` 。

本主题假设您之前已经完成了 [如何：在对话框中创建用户控件和宿主](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ，以及 [如何：创建用户控件和宿主 MDI 视图](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)。

### <a name="to-create-the-mfc-host-application"></a>创建 MFC 宿主应用程序

1. 打开在 [如何：创建用户控件和宿主 MDI 视图](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)中创建的 MFC 应用程序。

1. 将以下行添加到 `CMFC02View` MFC02View 中类声明的公共覆盖部分。

   `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. 添加 OnInitialupdate 的重写。

   显示 " **属性** " 窗口 (F4) 。 在 **类视图** ("CTRL + SHIFT + C") 中，选择 "CMFC02View 类"。 在 " **属性** " 窗口中，选择 "替代" 图标。 将列表向到 OnInitialUpdate。 单击下拉列表并选择 \<Add> 。 在 MFC02View 中。 请确保 OnInitialUpdate 函数的正文如下所示：

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. 生成并运行该项目。

   在 **“生成”** 菜单上，单击 **“生成解决方案”** 。

   在 " **调试** " 菜单上，单击 " **启动（不调试**）"。

   请注意，文本框现在已初始化。

## <a name="see-also"></a>请参阅

[以 MFC 视图的形式承载 Windows 窗体用户控件](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
