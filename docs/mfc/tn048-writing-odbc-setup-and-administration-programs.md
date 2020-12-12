---
description: 了解详细信息： TN048：编写 ODBC 安装程序和 MFC 数据库应用程序的管理程序
title: TN048：为 MFC 数据库应用程序编写 ODBC 安装和管理程序
ms.date: 11/04/2016
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
ms.openlocfilehash: bca8616bae8f7243b9e66b2eccc980afa3865842
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215100"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048：为 MFC 数据库应用程序编写 ODBC 安装和管理程序

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

使用 MFC 数据库类的应用程序将需要安装 ODBC 组件的安装程序。 它们可能还需要一个 ODBC 管理程序，该程序将检索有关可用驱动程序的信息，以指定默认驱动程序和配置数据源。 本说明介绍了如何使用 ODBC 安装程序 API 编写这些程序。

## <a name="writing-an-odbc-setup-program"></a><a name="_mfcnotes_writing_an_odbc_setup_program"></a> 编写 ODBC 安装程序

MFC 数据库应用程序要求 ODBC 驱动程序管理器 ( # A0) 和 ODBC 驱动程序能够访问数据源。 许多 ODBC 驱动程序还需要额外的网络和通信 Dll。 大多数 ODBC 驱动程序都附带了安装程序，该程序将安装所需的 ODBC 组件。 使用 MFC 数据库类的应用程序开发人员可以：

- 依靠驱动程序特定的安装程序安装 ODBC 组件。 这将不再需要开发人员的工作，只需重新发布驱动程序的安装程序即可。

- 或者，你可以编写自己的安装程序，它将安装驱动程序管理器和驱动程序。

ODBC 安装程序 API 可用于编写特定于应用程序的安装程序。 安装程序 API 中的函数由 ODBC 安装程序 DLL 实现，ODBCINST.DLL 在16位 Windows 上，并在 Win32 上 ODBCCP32.DLL。 应用程序可以 `SQLInstallODBC` 在安装程序 DLL 中调用，它将安装 odbc 驱动程序管理器、odbc 驱动程序以及任何所需的转换器。 然后，它在 NT) 上的 ODBCINST.INI 文件 (或注册表中记录已安装的驱动程序和转换器。 `SQLInstallODBC` 需要 ODBC 的完整路径。INF 文件，其中包含要安装的驱动程序列表，并说明了构成每个驱动程序的文件。 它还包含有关驱动程序管理器和转换器的类似信息。 ODBC.INF 文件通常由驱动程序开发人员提供。

程序还可以安装单个 ODBC 组件。 若要安装驱动程序管理器，程序首先 `SQLInstallDriverManager` 在安装程序 DLL 中调用，以获取驱动程序管理器的目标目录。 这通常是 Windows Dll 所在的目录。 然后，该程序使用 ODBC 的 [ODBC Driver Manager] 部分中的信息。用于将驱动程序管理器和相关文件从安装磁盘复制到此目录的 INF 文件。 若要安装单个驱动程序，程序首先 `SQLInstallDriver` 在安装程序 DLL 中调用，以将驱动程序规范添加到 NT) 上的 ODBCINST.INI 文件 (或注册表。 `SQLInstallDriver` 返回驱动程序的目标目录，通常是 Windows Dll 所在的目录。 然后，该程序使用 ODBC 的驱动程序部分中的信息。用于将驱动程序 DLL 和相关文件从安装磁盘复制到此目录的 INF 文件。

有关 ODBC 的详细信息。INF、ODBCINST.INI 和使用安装程序 API，请参阅 ODBC SDK *程序员参考，* 第19章，安装 ODBC 软件。

## <a name="writing-an-odbc-administrator"></a><a name="_mfcnotes_writing_an_odbc_administrator"></a> 编写 ODBC 管理员

MFC 数据库应用程序可以通过以下两种方式之一来设置和配置 ODBC 数据源，如下所示：

- 使用 ODBC 管理器 (作为程序或控制面板项) 提供。

- 创建自己的程序以配置数据源。

配置数据源的程序将对安装程序 DLL 执行函数调用。 安装程序 DLL 调用安装程序 DLL 以配置数据源。 每个驱动程序都有一个安装程序 DLL;它可以是驱动程序 DLL 本身，也可以是单独的 DLL。 如果支持，安装程序 DLL 会提示用户提供驱动程序连接到数据源和默认转换器所需的信息。 然后，它调用安装程序 DLL 和 Windows Api，以将此信息记录到 ODBC.INI 文件 (或注册表) 。

若要显示一个对话框，用户可以在该对话框中添加、修改和删除数据源，程序会 `SQLManageDataSources` 在安装程序 DLL 中调用。 从控制面板调用安装程序 DLL 时，将调用此函数。 若要添加、修改或删除数据源，请 `SQLManageDataSources` `ConfigDSN` 在安装程序 DLL 中调用与该数据源关联的驱动程序。 若要直接添加、修改或删除数据源，程序需要 `SQLConfigDataSource` 在安装程序 DLL 中调用。 该程序传递数据源的名称和指定要执行的操作的选项。 `SQLConfigDataSource``ConfigDSN`在安装 DLL 中调用，并从中传递参数 `SQLConfigDataSource` 。

有关详细信息，请参阅 ODBC SDK *程序员参考、* 章节23、安装 Dll 函数引用和第24章：安装程序 Dll 函数引用。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
