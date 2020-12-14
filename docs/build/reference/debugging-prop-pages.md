---
description: 了解更多： c + + 调试属性页
title: C + + 调试属性页
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 78115a6b-3799-4515-814e-8566b5bdc55d
f1_keywords:
- VC.Project.IVCLocalDebugPageObject.Command
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.IVCLocalDebugPageObject.Attach
- VC.Project.IVCLocalDebugPageObject.DebuggerType
- VC.Project.IVCLocalDebugPageObject.Environment
- VC.Project.IVCLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCLocalDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCLocalDebugPageObject.EnvironmentMerge
- VC.Project.IVCLocalDebugPageObject.SQLDebugging
- VC.Project.IVCLocalDebugPageObject.AmpDefaultAccelerator
- VC.Project.IVCRemoteDebugPageObject.RemoteCommand
- VC.Project.IVCRemoteDebugPageObject.CommandArguments
- VC.Project.IVCRemoteDebugPageObject.WorkingDirectory
- VC.Project.IVCRemoteDebugPageObject.RemoteMachine
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCRemoteDebugPageObject.DebuggerType
- VC.Project.IVCRemoteDebugPageObject.Environment
- VC.Project.IVCRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCRemoteDebugPageObject.Attach
- VC.Project.IVCRemoteDebugPageObject.SQLDebugging
- VC.Project.IVCRemoteDebugPageObject.DeploymentDirectory
- VC.Project.IVCRemoteDebugPageObject.AdditionalFiles
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCRemoteDebugPageObject.AmpDefaultAccelerator
- VC.Project.VCDebugSettings.WebBrowser.WebBrowserDebuggerHttpUrl
- VC.Project.VCDebugSettings.WebBrowser.DebuggerType
- VC.Project.IVCWebSvcDebugPageObject.HttpUrl
- VC.Project.IVCWebSvcDebugPageObject.DebuggerType
- VC.Project.IVCWebSvcDebugPageObject.SQLDebugging
ms.openlocfilehash: 16a7fec317485dd20a430baab9a413586f913fa3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201737"
---
# <a name="c-debugging-property-pages"></a>C + + 调试属性页

这些属性页位于 "**项目**  >  **属性**" "  >  **配置属性**" "  >  **调试**" 下。 在下拉控件中选择 "调试器类型"。 有关调试 c + + 代码的详细信息，请参阅 [教程：了解如何使用 Visual Studio 调试 c + + 代码](/visualstudio/debugger/getting-started-with-the-debugger-cpp) 和 [调试本机代码](/visualstudio/debugger/debugging-native-code)。

## <a name="local-windows-debugger-property-page"></a>"本地 Windows 调试器" 属性页

### <a name="command"></a>命令

要执行的调试命令。

### <a name="command-arguments"></a>命令参数

要传递给应用程序的命令行参数。

### <a name="working-directory"></a>工作目录

应用程序的工作目录。 默认情况下，包含项目文件的目录。

### <a name="attach"></a>附加

指定调试器是否应尝试在启动调试时附加到现有进程。

### <a name="debugger-type"></a>调试器类型

指定要使用的调试器类型。 如果设置为 "自动"，则将根据 exe 文件的内容选择调试器类型。

**选项**

- **仅限本机** -仅限本机
- **仅限托管**
- **混合** 混合
- **自动** 自动
- **脚本** -脚本
- **仅 gpu (C++ AMP)** -仅限 gpu (C++ AMP) 

### <a name="environment"></a>环境

指定要调试的程序的环境，或要与现有环境合并的变量。

### <a name="debugging-accelerator-type"></a>调试加速器类型

用于调试 GPU 代码的调试加速器类型。 当 GPU 调试程序处于活动状态时， (可用。 ) 

### <a name="gpu-default-breakpoint-behavior"></a>GPU 默认断点行为

设置 GPU 调试器中断的频率。

**选项**

- **每** 个弯曲一次中断一次
- 对于每个线程 **(（例如 cpu 行为**），每个线程) 中断 (如 cpu 行为) 

### <a name="merge-environment"></a>合并环境

将指定的环境变量与现有环境合并。

### <a name="sql-debugging"></a>SQL 调试

附加 SQL 调试器。

### <a name="amp-default-accelerator"></a>Amp 默认快捷键

覆盖 C++ AMP 的默认快捷键选择。 调试托管代码时，属性不适用。

## <a name="remote-windows-debugger-property-page"></a>"远程 Windows 调试器" 属性页

有关远程调试的详细信息，请参阅 [在 Visual Studio 中远程调试 Visual C++ 项目](/visualstudio/debugger/remote-debugging-cpp)。

### <a name="remote-command"></a>远程命令

要执行的调试命令。

### <a name="remote-command-arguments"></a>远程命令参数

要传递给应用程序的命令行参数。

### <a name="working-directory"></a>工作目录

应用程序的工作目录。 默认情况下，包含项目文件的目录。

### <a name="remote-server-name"></a>远程服务器名称

指定远程服务器名称。

### <a name="connection"></a>连接

指定连接类型。

**选项**

- **带 windows 身份验证的远程** -远程和 [windows 身份验证](/windows-server/security/windows-authentication/windows-authentication-overview)。
- **不带身份验证的远程远程** 身份验证（无身份验证）。

### <a name="debugger-type"></a>调试器类型

指定要使用的调试器类型。 如果设置为 "自动"，则将根据 exe 文件的内容选择调试器类型。

**选项**

- **仅限本机** -仅限本机
- **仅限托管**
- **混合** 混合
- **自动** 自动
- **脚本** -脚本
- **仅 gpu (C++ AMP)** -仅限 gpu (C++ AMP) 

### <a name="environment"></a>环境

指定要调试的程序的环境，或要与现有环境合并的变量。

### <a name="debugging-accelerator-type"></a>调试加速器类型

用于调试 GPU 代码的调试加速器类型。 当 GPU 调试程序处于活动状态时， (可用。 ) 

### <a name="gpu-default-breakpoint-behavior"></a>GPU 默认断点行为

设置 GPU 调试器中断的频率。

**选项**

- **每** 个弯曲一次中断一次
- 对于每个线程 **(（例如 cpu 行为**），每个线程) 中断 (如 cpu 行为) 

### <a name="attach"></a>附加

指定调试器是否应尝试在启动调试时附加到现有进程。

### <a name="sql-debugging"></a>SQL 调试

附加 SQL 调试器。

### <a name="deployment-directory"></a>部署目录

当在远程计算机上进行调试时，如果希望项目输出 (除了 PDB 文件) 要复制到远程计算机之外的内容，请在此指定路径。

### <a name="additional-files-to-deploy"></a>其他要部署的文件

在远程计算机上调试时，在此处指定的文件和目录 (除了项目输出) 会复制到部署目录（如果已指定）。

### <a name="deploy-visual-c-debug-runtime-libraries"></a>部署 Visual C++ 调试运行时库

指定是否为活动平台 (Win32、x64 或 ARM) 部署调试运行库。

### <a name="amp-default-accelerator"></a>Amp 默认快捷键

覆盖 C++ AMP 的默认快捷键选择。 调试托管代码时，属性不适用。

## <a name="web-browser-debugger-property-page"></a>Web 浏览器调试器属性页

### <a name="http-url"></a>HTTP URL

指定项目的 URL。

### <a name="debugger-type"></a>调试器类型

指定要使用的调试器类型。 如果设置为 "自动"，则将根据 exe 文件的内容选择调试器类型。

**选项**

- **仅限本机** -仅限本机
- **仅限托管**
- **混合** 混合
- **自动** 自动
- **脚本** -脚本

## <a name="web-service-debugger-property-page"></a>"Web 服务调试器" 属性页

### <a name="http-url"></a>HTTP URL

指定项目的 URL。

### <a name="debugger-type"></a>调试器类型

指定要使用的调试器类型。 如果设置为 "自动"，则将根据 exe 文件的内容选择调试器类型。

**选项**

- **仅限本机** -仅限本机
- **仅限托管**
- **混合** 混合
- **自动** 自动
- **脚本** -脚本

### <a name="sql-debugging"></a>SQL 调试

附加 SQL 调试器。
