---
description: 了解详细信息：链接器工具错误 LNK1168
title: 链接器工具错误 LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: 692bfbcc744307f32c8017b41ec27f5f421ea17c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253489"
---
# <a name="linker-tools-error-lnk1168"></a>链接器工具错误 LNK1168

无法打开 filename 进行写入

链接器无法写入 `filename`。 文件可能正在使用中且其文件句柄已被其他进程锁定，或者你可能没有对该文件或者对其所在的目录或网络共享的写入权限。 此错误通常是由暂时性情况引起的，例如，防病毒程序持有的锁、文件搜索索引过程或释放由 Visual Studio 生成系统持有的锁的延迟。

若要修复此问题，请验证 `filename` 文件句柄是否锁定以及你是否具有对此文件的写入权限。 如果它是可执行文件，则请验证它是否已在运行。

您可以使用 Windows SysInternals 实用工具 [句柄](/sysinternals/downloads/handle) 或 [进程资源管理器](/sysinternals/downloads/process-explorer) 来确定哪个进程具有文件句柄锁 `filename` 。 你还可以使用进程资源管理器释放开放式文件句柄上的锁。 有关如何使用这些实用工具的信息，请参阅它们附带的帮助文件。

如果文件被防病毒程序锁定，则可以通过防病毒程序从自动扫描中排除生成输出目录，从而修复此问题。 防病毒扫描程序通常当在文件系统中创建新文件时触发，在扫描继续时，它们持有文件上的锁。 有关如何从扫描中排除特定目录的详细信息，请参考防病毒程序文档。

如果文件被搜索索引服务锁定，则可通过从自动索引中排除生成输出目录来修复此问题。 有关详细信息，请参考索引服务的文档。 若要更改 Windows search 索引服务，请使用 Windows **控制面板** 中的 "**索引选项**"。 有关详细信息，请参阅 [Windows 10 中的搜索索引：常见问题](https://support.microsoft.com/help/4098843/windows-10-search-indexing-faq)。

如果可执行文件无法被生成进程覆盖，则可能被文件资源管理器锁定。 如果已禁用 **应用程序体验** 服务，则文件资源管理器可能会在一段较长的时间中一直保持到可执行文件句柄锁。 若要解决此问题，请运行 **services.msc** ，然后打开 "**应用程序体验**" 服务的 "**属性**" 对话框。 将 " **启动类型** " 从 " **已禁用** " 更改为 " **手动**"。
