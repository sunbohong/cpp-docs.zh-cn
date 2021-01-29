---
title: Launch.vs.json 架构参考 (C++)
description: 描述 `launch.vs.json` 文件的架构元素
ms.date: 12/02/2020
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: 0338f3c8c6bf9eff73a0464ad6c9aac777afacc2
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667457"
---
# <a name="launchvsjson-schema-reference-c"></a>Launch.vs.json 架构参考 (C++)

使用 launch.vs.json 文件配置调试参数  。 若要创建文件， 在“解决方案资源管理器”中右键单击可执行文件，然后选择“调试和启动设置”   。 选择与项目最匹配的选项，然后根据需要使用以下属性修改配置。 有关调试 CMake 项目的详细信息，请参阅[配置 CMake 调试会话](./configure-cmake-debugging-sessions.md)。

## <a name="default-properties"></a>默认属性

|properties|类型|说明|
|-|-|-|
|`args`|array|指定传递给已启动程序的命令行参数。|
|`buildConfigurations`|array| 一个键值对，指定要应用配置的生成模式的名称。 例如，`Debug` 或 `Release`，且要使用的配置根据所选生成模式确定。
|`currentDir`|string|指定生成目标的完整目录路径。 除非设置了此参数，否则将自动对此进行检测。|
|`cwd`|string|远程系统上将运行程序的目录的完整路径。 默认为  `"${debugInfo.defaultWorkingDirectory}"`|
|`debugType`|string|根据代码类型指定调试模式（本机、托管或混合）。 除非设置了此参数，否则会自动检测到此内容。 允许的值：`"native"`、`"managed"`、`"mixed"`。|
|`env`|array| 指定自定义环境变量的键值列表。 例如：`env:{"myEnv":"myVal"}`。|
|`inheritEnvironments`|array|指定从多个源继承的一组环境变量。 可以在 `CMakeSettings.json` 或 `CppProperties.json` 等文件中定义一些变量，并使它们可用于调试上下文 。  Visual Studio 16.4：使用 `env.VARIABLE_NAME` 语法，根据每个目标指定环境变量。 若要取消设置某个变量，请将它设置为 `"null"`。|
|`name`|string|指定“启动项”下拉列表中条目的名称。|
|`noDebug`|boolean|指定是否调试已启动程序。 如果没有指定，则此参数的默认值为 `false`。|
|`portName`|string|指定附加到正在运行的进程时的端口名称。|
| `program`|string|要执行的调试命令。 默认为  `"${debugInfo.fullTargetPath}"`。|
|`project`|string|指定项目文件的相对路径。 通常，调试 CMake 项目时不需要更改此值。 |
|`projectTarget`|string|指定生成 `project` 时调用的可选目标。 目标必须与“启动项”下拉列表中的名称匹配。|
|`stopOnEntry`|boolean|指定在启动进程并附加调试程序后是否立即中断。 此参数的默认值为 `false`。|
|`remoteMachine`|string|指定启动程序的远程计算机的名称。|
|`type`|string|指定项目是 `dll` 还是 `exe`（默认为 .exe）|

## <a name="c-linux-properties"></a>C++ Linux 属性

|properties|类型|说明|
|-|-|-|
|`program`|string|远程计算机上的程序可执行文件的完整路径。 使用 CMake 时，宏 `${debugInfo.fullTargetPath}` 可用作此字段的值。|
|`processId`|integer|要将调试程序附加到的可选进程 ID。|
|`sourceFileMap`|对象 (object)|传递给调试引擎的可选源文件映射。 格式：`{ "\<Compiler source location>": "\<Editor source location>" }` 或 `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }`。 示例：`{ "/home/user/foo": "C:\\foo" }` 或 `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`。 请参阅[源文件映射选项](#source_file_map_options)。|
|`additionalProperties`|string|其中一个 sourceFileMapOptions。 （请参阅下文。）|
|`MIMode`|string|指示 MIDebugEngine 将连接到的已启用 MI 的控制台调试程序的类型。 允许的值为 `"gdb"`、`"lldb"`。|
|`args`|array|传递给程序的命令行参数。|
|`environment`|array|要添加到程序环境的环境变量。 示例：`[ { "name": "squid", "value": "clam" } ]`。|
|`targetArchitecture`|string|调试对象的体系结构。 除非设置了此参数，否则将自动对此进行检测。 允许的值为 `x86`、`arm`、`arm64`、`mips`、`x64`、`amd64`、`x86_64`。|
|`visualizerFile`|string|调试此进程时要使用的 .natvis 文件。 此选项与 GDB 整齐打印不兼容。 如果使用此设置，请参阅 `"showDisplayString"`。|
|`showDisplayString`|boolean|指定 visualizerFile 时，`showDisplayString` 将启用显示字符串。 启用此选项会降低调试期间的性能。|
|`remoteMachineName`|string|托管 gdb 和要调试的程序的远程 Linux 计算机。 使用连接管理器添加新的 Linux 计算机。 使用 CMake 时，宏 `${debugInfo.remoteMachineName}` 可用作此字段的值。|
|`miDebuggerPath`|string|启用 MI 的调试程序（例如 gdb）的路径。 如果未指定，它将首先搜索调试程序的路径。|
|`miDebuggerServerAddress`|string|要连接到的已启用 MI 的调试程序服务器的网络地址。 示例：localhost:1234。|
|`setupCommands`|array|为设置基础调试程序而要执行一个或多个 GDB/LLDB 命令。 示例：`"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]`。 请参阅[启动安装程序命令](#launch_setup_commands)。|
|`customLaunchSetupCommands`|array|如果提供，则会使用一些其他命令替换用于启动目标的默认命令。 例如，为了附加到目标进程，可以是“-target-attach”。 空命令列表将启动命令替换为空内容，这在将启动选项作为命令行选项提供给调试程序时很有用。 示例：`"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]`。|
|`launchCompleteCommand`|string|调试程序完全设置好以后要执行的命令，用于使目标进程运行。 允许的值为“exec-run”、“exec-continue”、“None”。 默认值为“exec-run”。|
|`debugServerPath`|string|要启动的调试服务器的可选完整路径。 默认为“null”。|
|`debugServerArgs`|string|可选的调试服务器参数。 默认为“null”。|
|`filterStderr`|boolean|在 stderr 流中搜索服务器启动模式，并将 stderr 记录到调试输出。 默认为 `false`。|
|`coreDumpPath`|string|指定程序的核心转储文件的可选完整路径。 默认为“null”。|
externalConsole|boolean|如果为 true，则为调试对象启动控制台。 如果为 `false`，则不会启动任何控制台。 此设置的默认值为“`false`”。 由于技术原因，此选项在某些情况下被忽略。|
|`pipeTransport`|string|如果存在，则会告知调试程序使用其他可执行文件作为管道连接到远程计算机，此管道将在 Visual Studio 和已启用 MI 的调试程序（例如 gdb）之间中继标准输入/输出。 允许的值：一个或多个[管道传输选项](#pipe_transport_options)。|

## <a name="c-windows-remote-debug-and-deploy-properties"></a><a name="remote_deploy_debug"></a> C++ Windows 远程调试和部署属性

在远程计算机上调试和部署应用程序时使用。

|properties|类型|说明|
|-|-|-|
|`cwd`|string|远程计算机上的目标的工作目录。 使用 CMake 时，宏 `${debugInfo.defaultWorkingDirectory}` 可用作此字段的值。 默认值是调试程序/命令的目录。|
|`deploy`|string|指定要部署的额外文件或目录。 例如：<br> `"deploy": {"sourcePath":"<Full path to source file/directory on host machine>", "targetPath":"<Full destination path to file/directory on target machine>"}` |
|`deployDirectory`|string|项目输出自动部署到的远程计算机上的位置。 默认为 `C:\Windows Default Deploy Directory\<name of app>`|
|`deployDebugRuntimeLibraries`|string|指定是否为活动平台部署调试运行时库。 如果活动 configurationType 为 `"Debug"`，则默认为 `"true"`|
|`deployRuntimeLibraries`|string|指定是否为活动平台部署运行时库。 如果活动 configurationType 为 `"MinSizeRel"`、`"RelWithDebInfo"` 或 `"Release"`，则默认为 `"true"`。|
|`disableDeploy` | boolean | 指定是否应部署文件。 |
|`remoteMachineName`|string|指定启动程序的远程 ARM64 Windows 计算机的名称。 可能是服务器名称或远程计算机的 IP 地址。 |
|`authenticationType`|string|指定远程连接的类型。 可能值为 `"windows"` 和 `"none"`。 默认为 `"windows"`。 这应与在远程计算机上运行的远程调试器上指定的身份验证设置相匹配。|

## <a name="launch-setup-commands"></a><a name="launch_setup_commands"></a>启动安装程序命令

与 `setupCommands` 属性配合使用：

|properties|类型|说明|
|-|-|-|
|`text`|string|要执行的调试程序命令。|
|`description`|string|命令的可选说明。|
|`ignoreFailures`|boolean|如果为 true，则应忽略命令的失败。 默认为 `false`。|

## <a name="pipe-transport-options"></a><a name = "pipe_transport_options"></a>管道传输选项

与 `pipeTransport` 属性配合使用：

|properties|类型|说明|
|-|-|-|
|`pipeCwd`|string|管道程序工作目录的完全限定的路径。|
|`pipeProgram`|string|要执行的完全限定的管道命令。|
|`pipeArgs`|array|传递给管道程序用于配置连接的命令行参数。|
|`debuggerPath`|string|目标计算机上调试程序的完整路径，例如，/usr/bin/gdb。|
|`pipeEnv`|对象 (object)|传递给管道程序的环境变量。|
|`quoteArgs`|boolean|如果各个参数包含字符（例如空格或制表符），是否应将其加引号？ 如果为 `false`，则调试器命令将不再被自动引用。 默认为 `true`。|

## <a name="source-file-map-options"></a><a name="source_file_map_options"></a>源文件映射选项

与 `sourceFileMap` 属性配合使用：

|properties|类型|说明|
|-|-|-|
|`editorPath`|string|编辑器要查找的源代码的位置。|
|`useForBreakpoints`|boolean|设置断点时，应使用此源映射。 如果为 `false`，则只有文件名和行号用于设置断点。 如果为 `true`，则只有在使用此源映射时，才会使用文件的完整路径和行号设置断点。 否则，设置断点时将仅使用文件名和行号。 默认为 `true`。|
