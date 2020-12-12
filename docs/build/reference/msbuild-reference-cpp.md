---
description: 了解有关以下内容的详细信息： c + + 项目的 MSBuild 引用
title: Visual Studio 中 c + + 项目的 MSBuild 引用
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 898757c8b7f1427c36e68a7227ec145abab8d078
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190609"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ 项目的 MSBuild 参考

MSBuild 是 Visual Studio 中所有项目（包括 c + + 项目）的本机生成系统。 当你在 Visual Studio 集成开发环境 (IDE) 中生成项目时，它会调用 msbuild.exe 工具，该工具反过来会使用 .vcxproj 项目文件以及各种目标和属性文件。 通常，我们强烈建议使用 Visual Studio IDE 来设置项目属性和调用 MSBuild。 如果未正确完成，手动编辑项目文件可能导致严重问题。

如果由于某种原因要直接从命令行使用 MSBuild，请参阅 [从命令行使用 msbuild](../msbuild-visual-cpp.md)。 有关 MSBuild 的常规详细信息，请参阅 Visual Studio 文档中的 [msbuild](/visualstudio/msbuild/msbuild) 。

## <a name="in-this-section"></a>在本节中

[C++ 项目的 MSBuild 内部项](msbuild-visual-cpp-overview.md)<br/>
有关如何存储和使用属性和目标的信息。

[用于生成命令和属性的常用宏](common-macros-for-build-commands-and-properties.md)<br/>
介绍可用于定义路径和产品版本等属性的宏 (编译时常量) 。

[为 c + + 项目创建的文件类型](file-types-created-for-visual-cpp-projects.md)<br/>
描述 Visual Studio 为不同项目类型创建的各种文件。

[Visual Studio c + + 项目模板](visual-cpp-project-types.md)<br>
介绍可用于 c + + 的基于 MSBuild 的项目类型。

[C++ 新项模板](using-visual-cpp-add-new-item-templates.md)<br>
介绍可以添加到 Visual Studio 项目中的源文件和其他项。

[预编译标头文件](../creating-precompiled-header-files.md) 如何使用预编译头文件以及如何创建您自己的自定义预编译代码以加速生成时间。

[Visual Studio 项目属性参考](property-pages-visual-cpp.md)<br/>
在 Visual Studio IDE 中设置的项目属性的参考文档。

## <a name="see-also"></a>请参阅

[C/C++ 生成参考](c-cpp-building-reference.md)
