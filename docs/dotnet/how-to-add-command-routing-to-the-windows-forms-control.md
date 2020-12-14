---
description: 了解详细信息：如何：将命令路由添加到 Windows 窗体控件
title: 如何：向 Windows 窗体控件添加命令传送
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: b46087d7df3da5f402432731db4b994b257a385b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335418"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>如何：向 Windows 窗体控件添加命令传送

[CWinFormsView](../mfc/reference/cwinformsview-class.md) 将命令和更新-命令 UI 消息路由到用户控件，以允许它处理 MFC 命令 (例如，框架菜单项和工具栏按钮) 。

用户控件使用 [ICommandTarget：： Initialize](../mfc/reference/icommandtarget-interface.md#initialize) 来存储对中的命令源对象的引用 `m_CmdSrc` ，如下面的示例中所示。 若要使用 `ICommandTarget` ，必须添加对 mfcmifc80.dll 的引用。

`CWinFormsView` 处理几个常见的 MFC 视图通知，方法是将它们转发到托管用户控件。 这些通知包括 [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate)、 [OnUpdate](../mfc/reference/iview-interface.md#onupdate) 和 [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) 方法。

本主题假设您之前已经完成了 [如何：在对话框中创建用户控件和宿主](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ，以及 [如何：创建用户控件和宿主 MDI 视图](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)。

### <a name="to-create-the-mfc-host-application"></a>创建 MFC 宿主应用程序

1. 打开在 " [如何：创建用户控件并在对话框中承载"](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)中创建 Windows 窗体控件库。

1. 添加对 mfcmifc80.dll 的引用，你可以通过右键单击 **解决方案资源管理器** 中的项目节点，选择 " **添加**"、" **引用**"，然后浏览到 Microsoft Visual Studio 10.0 \ VC\atlmfc\lib.）来执行此操作。

1. 打开 UserControl1.Designer.cs 并添加以下 using 语句：

    ```
    using Microsoft.VisualC.MFC;
    ```

1. 同样，在 UserControl1.Designer.cs 中，更改以下行：

    ```
    partial class UserControl1
    ```

   更改为：

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. 将此添加为的类定义的第一行 `UserControl1` ：

    ```
    private ICommandSource m_CmdSrc;
    ```

1. 将以下方法定义添加到 `UserControl1` (我们将在下一步中创建 MFC 控件的 ID) ：

    ```
    public void Initialize (ICommandSource cmdSrc)
    {
       m_CmdSrc = cmdSrc;
       // need ID of control in MFC dialog and callback function
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));
    }

    private void singleMenuHandler (uint cmdUI)
    {
       // User command handler code
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");
    }
    ```

1. 打开在 [如何：创建用户控件和宿主 MDI 视图](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)中创建的 MFC 应用程序。

1. 添加将调用的菜单选项 `singleMenuHandler` 。

   转到 **资源视图** (Ctrl + Shift + E) ，展开 **菜单** 文件夹，然后双击 " **IDR_MFC02TYPE**"。 这会显示 "菜单编辑器"。

   将菜单选项添加到 " **视图** " 菜单的底部。 请注意 " **属性** " 窗口中的菜单选项的 ID。 保存文件。

   在 **解决方案资源管理器** 中，打开 Resource .h 文件，复制刚添加的菜单选项的 "ID" 值，并将该值粘贴为 `m_CmdSrc.AddCommandHandler` c # 项目的方法中的调用的第一个参数， `Initialize` `32771` 如果必要) ，请 (替换。

1. 生成并运行该项目。

   在 **“生成”** 菜单上，单击 **“生成解决方案”** 。

   在 " **调试** " 菜单上，单击 " **启动（不调试**）"。

   选择已添加的菜单选项。 请注意，调用了 .dll 中的方法。

## <a name="see-also"></a>请参阅

[以 MFC 视图的形式承载 Windows 窗体用户控件](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource 接口](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget 接口](../mfc/reference/icommandtarget-interface.md)
