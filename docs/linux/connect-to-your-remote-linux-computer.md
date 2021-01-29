---
title: 在 Visual Studio 中连接到你的目标 Linux 系统
description: 如何从 Visual Studio C++ 项目连接到远程 Linux 计算机或适用于 Linux 的 Windows 子系统。
ms.date: 01/8/2021
ms.openlocfilehash: 653a1832b4aac6b87c49102440181bb0e55a45a9
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667595"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>在 Visual Studio 中连接到你的目标 Linux 系统

::: moniker range="msvc-140"

Linux 支持在 Visual Studio 2017 及更高版本中提供。

::: moniker-end

::: moniker range="msvc-150"

可以将 Linux 项目配置为以远程计算机或适用于 Linux 的 Windows 子系统 (WSL) 为目标。 对于远程计算机和 WSL，需要在 Visual Studio 2017 中设置远程连接。

::: moniker-end

::: moniker range="msvc-160"

可以将 Linux 项目配置为以远程计算机或适用于 Linux 的 Windows 子系统 (WSL) 为目标。 对于远程计算机，需要在 Visual Studio 中设置远程连接。 若要连接到 WSL，请直接跳到[连接到 WSL](#connect-to-wsl) 部分。

::: moniker-end

::: moniker range=">=msvc-150"

如果你使用的是远程连接，Visual Studio 会在远程计算机上生成 C++ Linux 项目。 至于是物理计算机、云中的 VM，还是 WSL，这并不重要。
为了生成项目，Visual Studio 会将源代码复制到远程 Linux 计算机。 然后，代码会根据 Visual Studio 设置进行编译。

::: moniker-end

::: moniker range="msvc-160"

> [!NOTE]
> Visual Studio 2019 版本 16.5 及更高版本还支持与 Linux 系统进行符合美国联邦信息处理标准 (FIPS) 140-2 的安全加密连接，以用于远程开发。 若要使用符合 FIPS 的连接，请改为按照[设置符合 FIPS 的安全远程 Linux 开发](set-up-fips-compliant-secure-remote-linux-development.md)中的步骤操作。

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="set-up-the-ssh-server-on-the-remote-system"></a>在远程系统上设置 SSH 服务器

如果还没有在 Linux 系统上设置和运行 SSH，请按照以下步骤安装它。 本文中的示例结合使用 Ubuntu 18.04 LTS 和 OpenSSH 服务器版本 7.6。 不过，对于任何使用最新版 OpenSSH 的发行版，操作说明应该是相同的。

1. 在 Linux 系统上，安装并启动 OpenSSH 服务器：

   ```bash
   sudo apt install openssh-server
   sudo service ssh start
   ```

1. 若要让 SSH 服务器在系统启动时自动启动，请使用 systemctl 启用它：

   ```bash
   sudo systemctl enable ssh
   ```

## <a name="set-up-the-remote-connection"></a>设置远程连接

1. 在 Visual Studio 中，依次选择菜单栏上的“工具”>“选项”  ，以打开“选项”  对话框。 然后，依次选择“跨平台”>“连接管理器”  ，以打开“连接管理器”对话框。

   如果你以前没有在 Visual Studio 中设置过连接，Visual Studio 会在你首次生成项目时，为你打开“连接管理器”对话框。

1. 在“连接管理器”对话框中，选择“添加”  按钮，以添加新连接。

   ![连接管理器](media/settings_connectionmanager.png)

   在任一场景中，均会显示“连接到远程系统”窗口  。

   ![连接到远程系统](media/connect.png)

1. 输入以下信息：

   | 条目 | 描述
   | ----- | ---
   | **主机名**           | 目标设备的名称或 IP 地址
   | **端口**                | 运行 SSH 服务的端口，通常为 22
   | **用户名**           | 要进行身份验证的用户
   | **身份验证类型** | 同时支持密码和私钥
   | **密码**            | 输入的用户名的密码
   | **私钥文件**    | 为 ssh 连接创建的私钥文件
   | **密码**          | 与上面选择的私钥一起使用的密码

   可以使用密码或密钥文件和密码进行身份验证。 对于许多开发方案，密码身份验证已足够，但密钥文件更安全。 如果已有密钥对，可以重用它。 目前，Visual Studio 只支持将 RSA 和 DSA 密钥用于远程连接。

1. 选择“连接”按钮，尝试连接到远程计算机  。

   如果连接成功，Visual Studio 便会将 IntelliSense 配置为使用远程标头。 有关详细信息，请参阅[远程系统上标头的 IntelliSense](configure-a-linux-project.md#remote_intellisense)。

   如果连接失败，则需要更改的输入框的边框为红色。

   ![连接管理器错误](media/settings_connectionmanagererror.png)

   如果使用密钥文件进行身份验证，请确保目标计算机的 SSH 服务器正在运行且配置正确。

   ::: moniker-end

   ::: moniker range="msvc-160"

## <a name="supported-ssh-algorithms"></a>支持的 SSH 算法

从 Visual Studio 版本 16.9 开始，删除了对用于加密数据和交换密钥的不安全的旧版 SSH 算法的支持。 仅支持以下算法。 客户端到服务器和服务器到客户端的 SSH 通信都支持它们：

|算法类型|支持的算法|
|---|---|
| 加密| aes128-cbc</br>aes128-cbc</br>aes192-cbc</br>aes192-ctr</br>aes256-cbc</br>aes256-ctr|
| HMAC | hmac-sha2-256</br>hmac-sha2-256 |
| 密钥交换| diffie-hellman-group14-sha256</br>diffie-hellman-group16-sha512</br>diffie-hellman-group-exchange-sha256</br>ecdh-sha2-nistp256</br>ecdh-sha2-nistp384</br>ecdh-sha2-nistp521|
|主机密钥|ecdsa-sha2-nistp256</br>ecdsa-sha2-nistp384</br>ecdsa-sha2-nistp521</br>ssh-dss</br>ssh-rsa|

### <a name="configure-the-ssh-server"></a>配置 SSH 服务器

首先，介绍一些背景信息。 要使用的 SSH 算法无法从 Visual Studio 中进行选择， 而是在与 SSH 服务器的初始握手期间确定的。 每一端（客户端和服务器）都提供了它支持的算法列表，然后选择两端通用的第一个算法。 只要 Visual Studio 和服务器之间至少有一个用于加密、HMAC、密钥交换等的通用算法，连接就会成功。

Open SSH 配置文件 (sshd_config) 没有配置默认情况下要使用的算法。 当没有指定算法时，SSH 服务器应该使用安全的默认算法。 这些默认算法取决于 SSH 服务器的版本和供应商。  如果 Visual Studio 不支持这些默认算法，或者将 SSH 服务器配置为使用 Visual Studio 不支持的算法，则可能会看到如下错误：无法连接到远程系统。找不到通用的客户端到服务器 HMAC 算法。

大多数新式 Linux 分发版上的默认 SSH 服务器应该可以与 Visual Studio 一起即开即用。 但是，如果你运行的是配置为使用不安全的旧版算法的旧版 SSH 服务器，下面将解释如何更新到更安全的版本。

在以下示例中，SSH 服务器使用不安全的 `hmac-sha1` 算法，该算法不受 Visual Studio 16.9 支持。 如果 SSH 服务器使用 OpenSSH，则可以如下所示编辑 `/etc/ssh/sshd_config` 文件以启用更安全的算法。 对于其他 SSH 服务器，请参阅服务器文档以了解如何配置它们。

首先，请验证服务器正在使用的算法集是否包含 Visual Studio 支持的算法。 在远程计算机上运行以下命令，它将列出服务器支持的算法。

```bash
$ ssh -Q cipher; ssh -Q mac; ssh -Q kex; ssh -Q key
```

它将生成如下输出：

```bash
3des-cbc
aes128-cbc
aes192-cbc
aes256-cbc
...
ecdsa-sha2-nistp521-cert-v01@openssh.com
sk-ecdsa-sha2-nistp256-cert-v01@openssh.com
```

此输出将列出 SSH 服务器支持的所有加密、HMAC、密钥交换和主机密钥算法。 如果此列表不包括 Visual Studio 支持的算法，则需要先升级 SSH 服务器，然后再继续。

通过在远程计算机上编辑 `/etc/ssh/sshd_config`，可以启用 Visual Studio 支持的算法。 下面的示例演示如何将各种类型的算法添加到该配置文件中。

这些示例可以添加到 `/etc/ssh/sshd_config` 中的任何位置。 确保它们位于各自的行上。

编辑完文件后，重新启动 SSH 服务器（Ubuntu 上的 `sudo service ssh restart`），并尝试从 Visual Studio 再次连接。

#### <a name="cipher--example"></a>密码示例

添加：`Ciphers <algorithms to enable>`  
例如：`Ciphers aes128-cbc,aes256-cbc`

#### <a name="hmac-example"></a>HMAC 示例

添加：`MACs <algorithms to enable>`  
例如：`MACs hmac-sha2-256,hmac-sha2-512`

#### <a name="key-exchange-example"></a>密钥交换示例

添加：`KexAlgorithms <algorithms to enable>`  
例如：`KexAlgorithms ecdh-sha2-nistp256,ecdh-sha2-nistp384`

#### <a name="host-key-example"></a>主机密钥示例

添加：`HostKeyAlgorithms <algorithms to enable>`  
例如：`HostKeyAlgorithms ssh-dss,ssh-rsa`

## <a name="logging-for-remote-connections"></a>远程连接的日志记录

   可以启用日志记录来帮助排查连接问题。 在菜单栏上，依次选择“工具”>“选项”。 在“选项”对话框中，依次选择“跨平台”>“日志记录”：

   ![远程日志记录](media/remote-logging-vs2019.png)

   日志包括连接、发送到远程计算机的所有命令（其文本、退出代码和执行时间）以及从 Visual Studio 到 shell 的所有输出。 日志记录适用于 Visual Studio 中的任何跨平台 CMake 项目或基于 MSBuild 的 Linux 项目。

   可以配置是输出到文件，还是输出到“输出”窗口中的“跨平台日志记录”窗格内。 对于基于 MSBuild 的 Linux 项目，发送到远程计算机的 MSBuild 命令不会路由到“输出窗口”，因为它们在进程外发出。 它们将记录到前缀为“msbuild_”的文件。

## <a name="command-line-utility-for-the-connection-manager"></a>用于连接管理器的命令行实用工具  

**Visual Studio 2019 版本 16.5 或更高版本**：ConnectionManager.exe 是用于在 Visual Studio 之外管理远程开发连接的命令行实用工具。 它对于预配新开发计算机之类的任务非常有用。 你也可以使用它来设置 Visual Studio 进行持续集成。 有关 ConnectionManager 命令的示例和完整参考，请参阅 [ConnectionManager 参考](connectionmanager-reference.md)。  

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="tcp-port-forwarding"></a>TCP 端口转发

Visual Studio 的 Linux 支持依赖于 TCP 端口转发。 如果在远程系统上 TCP 端口转移处于禁用状态，Rsync 和 gdbserver 会受到影响。 如果你受此依赖关系的影响，则可以从开发者社区取消对此[建议票证](https://developercommunity2.visualstudio.com/t/shDonshshtsh-shrelysh-s/840265?space=62)投赞成票。

rsync 由基于 MSBuild 的 Linux 项目和 CMake 项目用来[将标题从远程系统复制到 Windows，以供 IntelliSense 使用](configure-a-linux-project.md#remote_intellisense)。 如果无法启用 TCP 端口转发，请禁用远程标头的自动下载。 要禁用它，请使用“工具”>“选项”>“跨平台”>“连接管理器”>“远程标头 IntelliSense 管理器”。 如果远程系统没有启用 TCP 端口转发，则当开始下载 IntelliSense 的远程标头时会出现此错误：

![标头错误](media/port-forwarding-headers-error.png)

Visual Studio 的 CMake 支持也使用 rsync 将源文件复制到远程系统。 如果无法启用 TCP 端口转发，则可以将 sftp 用作远程复制源方法。 sftp 通常会比 rsync 慢，但不依赖于 TCP 端口转发。 可以在 [CMake 设置编辑器](../build/cmakesettings-reference.md#additional-settings-for-cmake-linux-projects)中，借助 remoteCopySourcesMethod 属性来管理远程复制源方法。 如果在远程系统上禁用了 TCP 端口转发，则在第一次调用 rsync 时，会在 CMake 输出窗口中看到一条错误。

![rsync 错误](media/port-forwarding-copy-error.png)

gdbserver 可用于在嵌入式设备上进行调试。 如果无法启用 TCP 端口转发，则必须对所有远程调试方案使用 gdb。 在远程系统上调试项目时，默认情况下使用 gdb。

## <a name="connect-to-wsl"></a>连接到 WSL

::: moniker-end

::: moniker range="msvc-150"

在 Visual Studio 2017 中，使用用于远程 Linux 计算机的相同步骤连接到 WSL。 使用 localhost 作为主机名。

::: moniker-end

::: moniker range="msvc-160"

对结合使用 C++ 与[适用于 Linux 的 Windows 子系统 (WSL)](/windows/wsl/about)，Visual Studio 2019 版本 16.1 添加了本机支持。 这意味着可以直接在本地 WSL 安装上生成和调试。 不再需要添加远程连接或配置 SSH。 可在此处找到有关[如何安装 WSL](/windows/wsl/install-win10)的详细信息。

若要配置 WSL 安装，使其可与 Visual Studio 结合使用，则需安装以下工具：gcc 或 clang、gdb、make、ninja-build（仅适用于使用 Visual Studio 2019 版本 16.6 或更高版本的 CMake 项目）、rsync 和 zip。 你可以使用此命令将它们安装在使用 apt 的发行版上，这还将安装 g++ 编译器：

```bash
sudo apt install g++ gdb make ninja-build rsync zip
```

有关详细信息，请参阅[下载、安装和设置 Linux 工作负荷](download-install-and-setup-the-linux-development-workload.md)。

若要为 WSL 配置 MSBuild 项目，请参阅[配置 Linux 项目](configure-a-linux-project.md)。 若要为 WSL 配置 CMake 项目，请参阅[配置 Linux CMake 项目](cmake-linux-project.md)。 要按照分步说明使用 WSL 创建简单的控制台应用程序，请参阅关于 [C++ with Visual Studio 2019 and the Windows Subsystem for Linux (WSL)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)（结合使用 C++ 和 Visual Studio 2019 及适用于 Linux 的 Windows 子系统 (WSL)）的介绍性博客文章。

::: moniker-end

## <a name="see-also"></a>另请参阅

[配置 Linux 项目](configure-a-linux-project.md)\
[配置 Linux CMake 项目](cmake-linux-project.md)\
[部署、运行和调试 Linux 项目](deploy-run-and-debug-your-linux-project.md)\
[配置 CMake 调试会话](../build/configure-cmake-debugging-sessions.md)
