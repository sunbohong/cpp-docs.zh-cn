---
description: 了解更多： ATL 项目向导
title: ATL 项目向导
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.atl.com.overview
helpviewer_keywords:
- ATL projects, creating
- ATL Project Wizard
ms.assetid: 564d2aaf-5b8e-4c2a-a925-ca40a283ea34
ms.openlocfilehash: a254447d0590abd3d68090dac04c3b6134f94b19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158668"
---
# <a name="atl-project-wizard"></a>ATL 项目向导

 (ATL) 的活动模板库是一组基于模板的 c + + 类，用于简化小的、快速的 COM 对象。 ATL 项目向导创建一个项目，其中包含要包含 COM 对象的结构。

## <a name="overview"></a>概述

此向导页描述你正在创建的 [ATL 项目的当前应用程序设置](../../atl/reference/application-settings-atl-project-wizard.md) 。 默认情况下，该项目具有以下设置：

- 动态链接库指定服务器是 DLL，因此是进程内服务器。

- 特性化指定你的项目使用特性。

若要更改这些默认值，请单击向导左列中的 " **应用程序设置** "，并在 ATL 项目向导的相应页中进行更改。

有关默认项目设置（包括字符集的选择）以及链接默认值的信息，请参阅 [默认 ATL 项目配置](../../atl/reference/default-atl-project-configurations.md)。

创建 ATL 项目后，可以使用 Visual C++ [代码向导](../../ide/adding-functionality-with-code-wizards-cpp.md)将对象或控件添加到项目。 您可以使用代码向导对基本 ATL 项目执行以下类型的增强：

- [向 ATL 项目添加对象和控件](../../atl/reference/adding-objects-and-controls-to-an-atl-project.md)

- [在 ATL 项目中添加新接口](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)

- [向 ATL 项目添加 COM + 1.0 组件](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

此外，在创建和增强 ATL 项目时，请考虑以下任务：

- [使 ATL 对象不可创建](../../atl/reference/making-an-atl-object-noncreatable.md)

- [优化 ATL 项目的编译器](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

可以指定项目属性 (例如， [是否静态链接到](../../atl/programming-with-atl-and-c-run-time-code.md) " [项目属性](../../build/reference/general-property-page-project.md) " 页中的 CRT) ，还可以为 ATL 项目设置 [生成配置](/visualstudio/ide/understanding-build-configurations) 。

## <a name="see-also"></a>请参阅

[Visual Studio 项目 - C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual Studio 中的 C++ 项目类型](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL COM 对象的基本知识](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[用 ATL 和 C Run-Time 代码编程](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[教程](../../atl/active-template-library-atl-tutorial.md)
