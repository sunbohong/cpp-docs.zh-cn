---
description: 了解详细信息：如何：在对话框中创建用户控件和宿主
title: 如何：创建用户控件并将它承载在对话框中
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
ms.openlocfilehash: 400906344f47f7100e52319adb37c39d1fb370e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283954"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>如何：创建用户控件并将它承载在对话框中

本文中的步骤假设你要创建一个基于对话框的 ([CDialog 类](../mfc/reference/cdialog-class.md)) Microsoft 基础类 (MFC) 项目，但你也可以向现有 MFC 对话框添加 Windows 窗体控件支持。

### <a name="to-create-the-net-user-control"></a>创建 .NET 用户控件

1. 创建一个名为的 Visual c # Windows 窗体控件库项目 `WindowsFormsControlLibrary1` 。

   在“文件”菜单上，单击“新建”，然后单击“项目”。 在 **Visual c #** 文件夹中，选择 **Windows 窗体控件库**"。

   `WindowsFormsControlLibrary1`单击 **"确定"** 接受项目名称。

   默认情况下，.NET 控件的名称将为 `UserControl1` 。

1. 向添加子控件 `UserControl1` 。

   在 " **工具箱**" 中，打开 " **所有 Windows 窗体** " 列表。 将 " **按钮** " 控件拖动到 `UserControl1` 设计图面。

   同时添加 **TextBox** 控件。

1. 在 **解决方案资源管理器** 中，双击 " **UserControl1.Designer.cs** " 将其打开以进行编辑。 将文本框和按钮的声明从更改 `private` 为 `public` 。

1. 生成项目。

   在 **“生成”** 菜单上，单击 **“生成解决方案”** 。

### <a name="to-create-the-mfc-host-application"></a>创建 MFC 宿主应用程序

1. 创建 MFC 应用程序项目。

   在“文件”菜单上，单击“新建”，然后单击“项目”。 在 **Visual C++** 文件夹中，选择 " **MFC 应用程序**"。

   在“名称”框中键入 `MFC01`。 更改解决方案设置以 **添加到解决方案**。 单击 **“确定”** 。

   在 **MFC 应用程序向导** 中，对于 "应用程序类型"，选择 " **基于对话框**"。 接受剩余的默认设置，然后单击 " **完成**"。 这将创建一个具有 "MFC" 对话框的 MFC 应用程序。

1. 将占位符控件添加到 "MFC" 对话框。

   在 " **视图** " 菜单上，单击 **资源视图**。 在 **资源视图** 中，展开 **对话框** 文件夹并双击 `IDD_MFC01_DIALOG` 。 对话框资源将出现在 " **资源编辑器**" 中。

   在 " **工具箱**" 中，打开 " **对话框编辑器** " 列表。 将 **静态文本** 控件拖动到对话框资源。 **静态文本** 控件将用作 .net Windows 窗体控件的占位符。 将其大小调整为大约 Windows 窗体控件的大小。

   在 "**属性**" 窗口中，将 "**静态文本**" 控件的 **ID** 更改为， `IDC_CTRL1` 并将 " **TabStop** " 属性更改为 **True**。

1.  (CLR) 支持配置公共语言运行时的项目。

   在 **解决方案资源管理器** 中，右键单击 "MFC01" 项目节点，然后单击 " **属性**"。

   在 " **属性页** " 对话框中的 " **配置属性**" 下，选择 " **常规**"。 在 " **项目默认值** " 部分中，将 " **公共语言运行时支持** " 设置为 **公共语言运行时支持 (/clr)**。

   在 " **配置属性**" 下，展开 " **c/c + +** " 并选择 " **常规** " 节点。 将 **调试信息格式** 设置为 **程序数据库 (/zi)**。

   选择 " **代码生成** " 节点。 将 " **启用最小重新生成** " 设置为 " **无 (/Gm-)**"。 还将 **基本运行时检查** 设置为 **默认值**。

   单击“确定”应用更改。

1. 添加对 .NET 控件的引用。

   在 **解决方案资源管理器** 中，右键单击 "MFC01" 项目节点，然后单击 " **添加**"、" **引用**"。 在 **属性页** 上，单击 **"添加新引用**"，选择 "**项目**" 选项卡下的 " **WindowsFormsControlLibrary1** (") ，然后单击 **"确定"**。 这会添加一个 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 编译器选项形式的引用，以便程序进行编译。 它还将 WindowsFormsControlLibrary1.dll 的副本放在 \MFC01\ 项目文件夹中，以便程序运行。

1. 在 Stdafx.h 中，查找以下行：

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   在上面添加以下行：

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. 添加代码以创建托管控件。

   首先，声明托管控件。 在 MFC01Dlg 中，请前往对话框类的声明，并在受保护的范围内为用户控件添加数据成员，如下所示。

    ```
    class CMFC01Dlg : public CDialog
    {
       // ...
       // Data member for the .NET User Control:
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;
    ```

   接下来，提供托管控件的实现。 在 MFC01Dlg 中，在 "MFC 应用程序向导" 生成的对话框 "重写" 中 `CMFC01Dlg::DoDataExchange` (不 `CAboutDlg::DoDataExchange` 是，它在) 的同一文件中，添加以下代码以创建托管控件，并将其与静态占位符 IDC_CTRL1 相关联。

    ```
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
    {
       CDialog::DoDataExchange(pDX);
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);
    }
    ```

1. 生成并运行该项目。

   在 **解决方案资源管理器** 中，右键单击 **MFC01** ，然后单击 " **设为启动项目**"。

   在 **“生成”** 菜单上，单击 **“生成解决方案”** 。

   在 " **调试** " 菜单上，单击 " **启动（不调试**）"。 MFC 对话框应显示 Windows 窗体控件。

## <a name="see-also"></a>请参阅

[在 MFC 对话框中承载 Windows 窗体用户控件](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)
