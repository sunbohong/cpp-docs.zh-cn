---
description: 了解有关以下内容的详细信息： ActiveX 控件容器：对 activex 控件容器中的 ActiveX 控件编程
title: ActiveX 控件容器：对 ActiveX 控件容器中的 ActiveX 控件编程
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
ms.openlocfilehash: 34a5a2aaa1d7ec940ea31ae2fbe8c89ba3d84818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251006"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX 控件容器：对 ActiveX 控件容器中的 ActiveX 控件编程

本文介绍了访问嵌入的 ActiveX 控件的公开 [方法](../mfc/mfc-activex-controls-methods.md) 和 [属性](../mfc/mfc-activex-controls-properties.md) 的过程。

>[!IMPORTANT]
> ActiveX 是一种不能用于新开发的旧技术。 有关取代 ActiveX 的新式技术的详细信息，请参阅 [Activex 控件](activex-controls.md)。

基本上，你将执行以下步骤：

1. 使用库在[activex 容器项目中插入 activex 控件](../mfc/inserting-a-control-into-a-control-container-application.md)。

1. 定义与 ActiveX 控件包装器类相同的类型的[成员变量](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (或其他形式的访问) 。

1. 使用包装类的预定义成员函数[对 ActiveX 控件进行编程](#_core_programming_the_activex_control)。

对于此讨论，假设已创建了一个基于对话框的项目 (名为容器) ，并支持 ActiveX 控件。 将 Circ 示例控件 Circ 添加到生成的项目。

将 Circ 控件插入到项目 (步骤 1) 中后，将 Circ 控件的一个实例插入到应用程序的主对话框中。

## <a name="procedures"></a>过程

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>向对话框模板添加 Circ 控件

1. 加载 ActiveX 控件容器项目。 对于本示例，请使用 `Container` 项目。

1. 单击 "资源视图" 选项卡。

1. 打开 **对话框** 文件夹。

1. 双击 main 对话框模板。 对于本示例，请使用 **IDD_CONTAINER_DIALOG**。

1. 单击工具箱上的 "Circ 控件" 图标。

1. 单击对话框中的某个位置可插入 Circ 控件。

1. 从 " **文件** " 菜单中，选择 " **全部保存** " 以保存对对话框模板的所有修改。

## <a name="modifications-to-the-project"></a>对项目的修改

为了使容器应用程序能够访问 Circ 控件，Visual C++ 自动将包装类添加 (`CCirc`) 实现文件 (。CPP) 到容器项目，包装类标头 (。H) 文件到对话框头文件：

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a> 包装器类标头 (。H) 文件

为获取和设置属性 (并为 Circ 控件调用方法) ， `CCirc` 包装类提供所有公开的方法和属性的声明。 在此示例中，在 CIRC 中找到了这些声明。 下面的示例是类 `CCirc` 的一部分，用于定义 ActiveX 控件的公开接口：

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

然后，可以使用常规 c + + 语法从应用程序的其他过程中调用这些函数。 有关使用此成员函数设置来访问控件的方法和属性的详细信息，请参阅对 [ActiveX 控件编程](#_core_programming_the_activex_control)部分。

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a> 对项目的成员变量修改

将 ActiveX 控件添加到项目并将其嵌入到对话框容器中后，项目的其他部分便可访问该控件。 访问该控件的最简单方法是创建对话框类的 [成员变量](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) ， `CContainerDlg` (步骤 2) ，这与通过 Visual C++ 添加到项目中的包装类的类型相同。 然后，可以使用该成员变量随时访问嵌入控件。

当 " **添加成员变量** " 对话框将 *m_circctl* 成员变量添加到项目中时，它还会将以下行添加到头文件 (。类的 H) `CContainerDlg` ：

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

此外，对 **DDX_Control** 的调用会自动添加到的 `CContainerDlg` 实现 `DoDataExchange` ：

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a> 对 ActiveX 控件编程

此时，您已将 ActiveX 控件插入对话框模板中，并为其创建了一个成员变量。 你现在可以使用通用 c + + 语法来访问嵌入控件的属性和方法。

如 [包装类标头 ( 所述 (。H) 文件](#_core_the_wrapper_class_header_28h29_file)) ， ( 头文件。用于包装类的 H) `CCirc` ，在本例中为 CIRC。H，包含成员函数的列表，您可以使用这些函数来获取和设置任何公开的属性值。 还提供了公开方法的成员函数。

用于修改控件属性的常见位置是在 `OnInitDialog` 主对话框类的成员函数中。 此函数在对话框显示之前调用，用于初始化其内容（包括其任何控件）。

下面的代码示例使用 *m_circctl* 成员变量来修改嵌入式 Circ 控件的 Caption 和 CircleShape 属性：

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>请参阅

[ActiveX 控件容器](../mfc/activex-control-containers.md)
