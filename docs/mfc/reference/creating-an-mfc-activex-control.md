---
title: 创建 MFC ActiveX 控件
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: 19e9ca6f985423bb01a8dea38988c5dcf7285683
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505967"
---
# <a name="creating-an-mfc-activex-control"></a>创建 MFC ActiveX 控件

ActiveX 控制程序是设计用于向父应用程序授予特定类型的功能的模块化程序。 例如，您可以创建一个控件（例如在对话框中使用的按钮），或创建要在网页中使用的工具栏。

>[!IMPORTANT]
> ActiveX 是一种不能用于新开发的旧技术。 有关详细信息，请参阅 [ActiveX 控件](../activex-controls.md)。

创建 MFC ActiveX 控件的最简单方法是使用 [Mfc Activex 控件向导](../../mfc/reference/mfc-activex-control-wizard.md)。

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>使用 MFC ActiveX 控件向导创建 MFC ActiveX 控件

1. 按照帮助主题 [创建 Mfc 应用程序](creating-an-mfc-application.md) 中的说明操作，但从可用模板列表中选择 " **MFC ActiveX 控件** "。

1. 使用 MFC ActiveX 控件向导定义 [应用程序设置](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)、 [控件名称](../../mfc/reference/control-names-mfc-activex-control-wizard.md)和 [控件设置](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 。

    > [!NOTE]
    >  跳过此步骤可保留向导的默认设置。

1. 单击“完成”关闭向导并在开发环境中打开新项目****。

创建项目后，可以在 **解决方案资源管理器**中查看创建的文件。 有关向导为项目创建的文件的更多信息，请参见项目生成的文件 ReadMe.txt。 有关文件类型的详细信息，请参阅[为 Visual Studio C++ 项目创建的文件类型](../../build/reference/file-types-created-for-visual-cpp-projects.md)。

创建项目后，可以使用代码向导添加 [函数](../../ide/adding-a-member-function-visual-cpp.md#add-member-function-wizard)、 [变量](../../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard)、 [事件](../../ide/adding-an-event-visual-cpp.md#add-event-wizard)、 [属性](../../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)和 [方法](../../ide/adding-a-method-visual-cpp.md#add-method-wizard)。 有关自定义 ActiveX 控件的详细信息，请参阅 [MFC ActiveX 控件](../../mfc/mfc-activex-controls.md)。

## <a name="see-also"></a>请参阅

[用代码向导添加功能](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[属性页](../../build/reference/property-pages-visual-cpp.md)
