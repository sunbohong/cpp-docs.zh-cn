---
description: 了解有关如何：使用/clr 编译 MFC 和 ATL 代码的详细信息
title: 如何：使用-clr 编译 MFC 和 ATL 代码
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], interoperability
- ATL [C++], interoperability
- mixed assemblies [C++], MFC code
- mixed assemblies [C++], ATL code
- /clr compiler option [C++], compiling ATL and MFC code
- interoperability [C++], /clr compiler option
- regular MFC DLLs [C++], /clr compiler option
- interop [C++], /clr compiler option
- extension DLLs [C++], /clr compiler option
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
ms.openlocfilehash: 67a861dac3b4c4b454f4fbde4a500c3677ce0e25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304488"
---
# <a name="how-to-compile-mfc-and-atl-code-by-using-clr"></a>如何：使用 /clr 编译 MFC 和 ATL 代码

本主题讨论如何编译现有的 MFC 和 ATL 程序以面向公共语言运行时。

### <a name="to-compile-an-mfc-executable-or-regular-mfc-dll-by-using-clr"></a>使用/clr 编译 MFC 可执行文件或常规 MFC DLL

1. 右键单击 " **解决方案资源管理器** 中的项目，然后单击" **属性**"。

1. 在 " **项目属性** " 对话框中，展开 " **配置属性** " 旁边的节点，然后选择 " **常规**"。 在右窗格中的 " **项目默认值**" 下，将 " **公共语言运行时支持** " 设置为 **(/Clr) 的公共语言运行时支持**。

   在同一个窗格中，请确保在 **共享 DLL 中****使用 mfc。**

1. 在 " **配置属性**" 下，展开 " **c/c + +** " 旁边的节点，然后选择 " **常规**"。 请确保将 " **调试信息格式** " 设置为 " **程序数据库/zi** (不) **/zi** "。

1. 选择 " **代码生成** " 节点。 将 " **启用最小重新生成** " 设置为 " **无 (/Gm-)**"。 还将 **基本运行时检查** 设置为 **默认值**。

1. 在 " **配置属性**" 下，选择 " **c/c + +** "，然后选择 **代码生成**。 请确保将 " **运行时库** " 设置为 **多线程调试 dll (/MDd)** 或 **多线程 dll (/md)**。

1. 在 Stdafx.h 中，添加以下行。

    ```
    #using <System.Windows.Forms.dll>
    ```

### <a name="to-compile-an-mfc-extension-dll-by-using-clr"></a>使用/clr 编译 MFC 扩展 DLL

1. 按照 "使用/clr 编译 MFC 可执行文件或常规 MFC DLL" 中的步骤进行操作。

1. 在 " **配置属性**" 下，展开 **c/c + +** 旁边的节点，然后选择 " **预编译标头**"。 将 " **创建/使用预编译标头** " 设置为 **不使用预编译头**。

   作为替代方法，在 **解决方案资源管理器** 中，右键单击 stdafx.h，然后单击 " **属性**"。 在 " **配置属性**" 下，展开 " **c/c + +** " 旁边的节点，然后选择 " **常规**"。 将 **具有公共语言运行时支持的编译** 设置为 **无公共语言运行时支持**。

1. 对于包含 DllMain 和它调用的任何内容的文件，请在 **解决方案资源管理器** 中右键单击该文件，然后单击 " **属性**"。 在 " **配置属性**" 下，展开 " **c/c + +** " 旁边的节点，然后选择 " **常规**"。 在右窗格中的 " **项目默认值**" 下，将 **具有公共语言运行时支持的编译** 设置为 **无公共语言运行时支持**。

### <a name="to-compile-an-atl-executable-by-using-clr"></a>使用/clr 编译 ATL 可执行文件

1. 在 **解决方案资源管理器** 中，右键单击项目，然后单击 " **属性**"。

1. 在 " **项目属性** " 对话框中，展开 " **配置属性** " 旁边的节点，然后选择 " **常规**"。 在右窗格中的 " **项目默认值**" 下，将 " **公共语言运行时支持** " 设置为 **(/Clr) 的公共语言运行时支持**。

1. 在 " **配置属性**" 下，展开 " **c/c + +** " 旁边的节点，然后选择 " **常规**"。 请确保将 " **调试信息格式** " 设置为 " **程序数据库/zi** (不) **/zi** "。

1. 选择 " **代码生成** " 节点。 将 " **启用最小重新生成** " 设置为 " **无 (/Gm-)**"。 还将 **基本运行时检查** 设置为 **默认值**。

1. 在 " **配置属性**" 下，选择 " **c/c + +** "，然后选择 **代码生成**。 请确保将 " **运行时库** " 设置为 **多线程调试 dll (/MDd)** 或 **多线程 dll (/md)**。

1. 对于每个 MIDL 生成的文件 (C files) ，在 **解决方案资源管理器** 中右键单击该文件，然后单击 " **属性**"。 在 " **配置属性**" 下，展开 " **c/c + +** " 旁边的节点，然后选择 " **常规**"。 将 **具有公共语言运行时支持的编译** 设置为 **无公共语言运行时支持**。

### <a name="to-compile-an-atl-dll-by-using-clr"></a>使用/clr 编译 ATL DLL

1. 按照 "使用/clr 编译 ATL 可执行文件" 部分中的步骤进行操作。

1. 在 " **配置属性**" 下，展开 **c/c + +** 旁边的节点，然后选择 " **预编译标头**"。 将 " **创建/使用预编译标头** " 设置为 **不使用预编译头**。

   作为替代方法，在 **解决方案资源管理器** 中，右键单击 stdafx.h，然后单击 " **属性**"。 在 " **配置属性**" 下，展开 " **c/c + +** " 旁边的节点，然后选择 " **常规**"。 将 **具有公共语言运行时支持的编译** 设置为 **无公共语言运行时支持**。

1. 对于包含 DllMain 和它调用的任何内容的文件，请在 **解决方案资源管理器** 中右键单击该文件，然后单击 " **属性**"。 在 " **配置属性**" 下，展开 " **c/c + +** " 旁边的节点，然后选择 " **常规**"。 在右窗格中的 " **项目默认值**" 下，将 **具有公共语言运行时支持的编译** 设置为 **无公共语言运行时支持**。

## <a name="see-also"></a>请参阅

[混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md)
