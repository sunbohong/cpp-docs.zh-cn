---
title: 在 Visual Studio 中创建 CMake Linux 项目
description: 如何在 Visual Studio 中创建 Linux CMake 项目
ms.date: 08/06/2020
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 5753dbb37c11686becb3e141261284b68468a3bc
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507958"
---
# <a name="create-a-cmake-linux-project-in-visual-studio"></a>在 Visual Studio 中创建 CMake Linux 项目

::: moniker range="vs-2015"
Linux 支持在 Visual Studio 2017 及更高版本中提供。 若要查看这些版本的文档，请将目录上方的“版本”下拉列表设置为“Visual Studio 2017”或“Visual Studio 2019”。
::: moniker-end

::: moniker range=">=vs-2017"

建议为跨平台或将设为开源的项目使用 CMake。 可以使用 CMake 项目在 Windows、适用于 Linux 的 Windows 子系统 (WSL) 和远程系统上生成和调试相同源代码。

## <a name="before-you-begin"></a>开始之前

首先，请确保已安装 Visual Studio Linux 工作负载，包括 CMake 组件。 它属于 Visual Studio 安装程序中的“使用 C++ 的 Linux 开发”工作负载。 如果不确定是否安装了此项，请参阅[在 Visual Studio 中安装 C++ Linux 工作负载](download-install-and-setup-the-linux-development-workload.md)。

此外，请确保在远程计算机上安装了以下项：

- gcc
- gdb
- rsync
- zip
- ninja-build（Visual Studio 2019 或更高版本）
::: moniker-end

::: moniker range="vs-2017"
使用 Visual Studio 中的 CMake 支持需要 CMake 3.8 中引入的服务器模式支持。 对于 Microsoft 提供的 CMake 变体，请在 [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) 中下载最新的预生成二进制文件。

二进制文件安装在 `~/.vs/cmake` 中。 部署二进制文件后，项目将自动重新生成。 如果由 CMakeSettings.json 中的 `cmakeExecutable` 字段指定的 CMake 无效（不存在或是不受支持的版本）且预生成二进制文件存在，则 Visual Studio 将忽略 `cmakeExecutable` 并使用预生成二进制文件。

Visual Studio 2017 无法从头开始创建 CMake 项目，但你可以打开包含现有 CMake 项目的文件夹，如下一节中所述。
::: moniker-end

::: moniker range=">=vs-2019"
可以使用 Visual Studio 2019 在远程 Linux 系统或 WSL 上生成和调试，CMake 将在该系统上调用。 应在目标计算机上安装 Cmake 版本 3.14 或更高版本。

请确保目标计算机具有最新版本的 CMake。 发行版的默认包管理器提供的版本通常不够新，不足以支持 Visual Studio 所需的所有功能。 Visual Studio 2019 会检测 Linux 系统上是否安装了最新版本的 CMake。 如果未找到，Visual Studio 将在编辑器窗格顶部显示一个信息栏。 它用于从 [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) 为你安装 CMake。

使用 Visual Studio 2019，可以从头开始创建 CMake 项目，或打开现有的 CMake 项目。 若要创建新 CMake 项目，请按照下面的说明进行操作。 或者跳到[打开 CMake 项目文件夹](#open-a-cmake-project-folder)（如果已有 CMake 项目）。

## <a name="create-a-new-linux-cmake-project"></a>创建新的 Linux CMake 项目

若要在 Visual Studio 2019 中创建新的 Linux CMake 项目，请执行以下操作：

1. 在 Visual Studio 中选择“**文件 > 新建项目**”，或按 **Ctrl + Shift + N**。
1. 将“语言”设置为“C++”，然后搜索“CMake” 。 然后，选择“下一步”。 输入“名称”和“位置”，然后选择“创建”  。

或者，可以在 Visual Studio 2019 中打开自己的 CMake 项目。 下面的部分说明如何执行此操作。

Visual Studio 创建一个最小的 CMakeLists.txt 文件，其中只包含可执行文件的名称和所需的最小 CMake 版本。 可以按自己喜欢的方式手动编辑此文件；Visual Studio 永远不会覆盖所做的更改。

为了帮助你在 Visual Studio 2019 中了解、编辑和创作 CMake 脚本，请参阅以下资源：

- [Visual Studio 中的 CMake 编辑器内文档](https://devblogs.microsoft.com/cppblog/in-editor-documentation-for-cmake-in-visual-studio/)
- [CMake 脚本的代码导航](https://devblogs.microsoft.com/cppblog/code-navigation-for-cmake-scripts/)
- [在 CMake 项目中轻松添加、删除和重命名文件和目标](https://devblogs.microsoft.com/cppblog/easily-add-remove-and-rename-files-and-targets-in-cmake-projects/)
::: moniker-end

::: moniker range=">=vs-2017"

## <a name="open-a-cmake-project-folder"></a>打开 CMake 项目文件夹

打开包含现有 CMake 项目的文件夹时，Visual Studio 会使用 CMake 缓存中的变量来自动配置 IntelliSense 和生成。 本地配置和调试设置将存储在 JSON 文件中。 可以选择与使用 Visual Studio 的其他人共享这些文件。

Visual Studio 不会修改 CMakeLists.txt 文件。 这使得处理同一项目的其他人员可以继续使用其现有工具。 在保存对 CMakeLists.txt 的编辑或在某些情况下保存对 CMakeSettings.json 的编辑时，Visual Studio 会重新生成缓存。 如果使用的是“现有缓存”配置，则 Visual Studio 不会修改缓存。

有关 Visual Studio 中的 CMake 支持的常规信息，请参阅 [Visual Studio 中的 CMake 项目](../build/cmake-projects-in-visual-studio.md)。 在继续之前，请先阅读相关内容。

首先，在主菜单中选择“文件” > “打开” > “文件夹”，或在[开发人员命令提示](../build/building-on-the-command-line.md)窗口中键入 `devenv.exe <foldername>`。 打开的文件夹中应该有一个 CMakeLists.txt 文件，以及你的源代码。

以下示例显示了一个简单的 CMakeLists.txt 文件和 .cpp 文件：

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt：

```txt
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="next-steps"></a>后续步骤

[配置 Linux CMake 项目](cmake-linux-configure.md)

## <a name="see-also"></a>请参阅

[Visual Studio 中的 CMake 项目](../build/cmake-projects-in-visual-studio.md)<br/>
::: moniker-end
