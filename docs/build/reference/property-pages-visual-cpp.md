---
description: 了解更多相关信息： Windows c + + 项目属性页引用
title: Windows c + + 项目属性页引用-Visual Studio
ms.date: 08/28/2019
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
ms.openlocfilehash: 30e8f33f09242779529d368fbafc72ee66a0264f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225734"
---
# <a name="windows-c-project-property-page-reference"></a>Windows c + + 项目属性页引用

在 Visual Studio 中，通过项目的属性页指定编译器和链接器选项、文件路径和其他生成设置。 可用的属性页和属性页取决于项目类型。 例如，生成文件项目具有一个不在 MFC 或 Win32 控制台项目中的 NMake 属性页。 若要打开 **属性页**，请从主菜单中选择 "**项目**  >  **属性**"，或右键单击 "**解决方案资源管理器** 中的项目节点，然后选择"**属性**"。 单个文件还具有属性页，使您可以为该文件设置编译和生成选项。 下图显示了 MFC 项目的属性页。

![C + + 项目的属性页](media/example-prop-page.png)

本部分提供属性页本身的快速参考。 在属性页中公开的选项和设置已更完整地记录在各自的主题中，并从属性页主题链接。 有关项目属性的详细信息，请参阅 [在 Visual Studio 中设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

有关 Linux 项目中的属性页，请参阅 [Linux c + + 属性页引用](../../linux/prop-pages-linux.md)。

## <a name="in-this-section"></a>本节内容

- [ (项目的常规属性页) ](general-property-page-project.md)
- [“常规”属性页（文件）](general-property-page-file.md)
- ["高级" 属性页](advanced-property-page.md)
- ["VC + + 目录" 属性页](vcpp-directories-property-page.md)
- [链接器属性页](linker-property-pages.md)
- [清单工具属性页](manifest-tool-property-pages.md)
- [HLSL 属性页](hlsl-property-pages.md)
- ["命令行" 属性页](command-line-property-pages.md)
- ["自定义生成步骤" 属性页：常规](custom-build-step-property-page-general.md)
- [添加引用](../adding-references-in-visual-cpp-projects.md)
- ["托管资源" 属性页](managed-resources-property-page.md)
- [MIDL 属性页](midl-property-pages.md)
- [NMake 属性页](nmake-property-page.md)
- [资源属性页](resources-property-pages.md)
- ["Web 引用" 属性页](web-references-property-page.md)
- ["XML 数据生成器工具" 属性页](xml-data-generator-tool-property-page.md)
- ["XML 文档生成器工具" 属性页](xml-document-generator-tool-property-pages.md)

## <a name="see-also"></a>请参阅

[如何：创建和移除项目依赖项](/visualstudio/ide/how-to-create-and-remove-project-dependencies)<br/>
[如何：创建和编辑配置](/visualstudio/ide/how-to-create-and-edit-configurations)<br/>
[Linux c + + 属性页引用](../../linux/prop-pages-linux.md)
