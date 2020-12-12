---
description: 了解详细信息：应用程序设置、MFC DLL 向导
title: MFC DLL 向导的应用程序设置
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.appset
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
ms.openlocfilehash: da9579ef9a834fa0c2362b1569c2efa808132faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322793"
---
# <a name="application-settings-mfc-dll-wizard"></a>MFC DLL 向导的应用程序设置

使用 MFC DLL 向导的此页可以设计基本功能并将其添加到新的 MFC DLL 项目。

## <a name="dll-type"></a>DLL 类型

选择要创建的 DLL 类型。

- **使用共享 MFC DLL 的规则 MFC DLL**

   选择此选项可以将 MFC 库作为共享 DLL 链接到程序。 使用此选项时，无法在 DLL 和调用应用程序之间共享 MFC 对象。 程序在运行时调用 MFC 库。 如果程序包含多个使用 MFC 库的执行文件，则此选项会降低程序的磁盘和内存要求。 Win32 和 MFC 程序都可以调用 DLL 中的函数。 必须重新分发具有此类型项目的 MFC DLL。

- **带有 MFC 静态链接的规则 MFC DLL**

   选择此选项可在生成时将程序静态链接到 MFC 库。 Win32 和 MFC 程序都可以调用 DLL 中的函数。 虽然此选项会增加程序的大小，但不需要重新分发具有此类型项目的 MFC DLL。 不能在 DLL 和调用应用程序之间共享 MFC 对象。

- **MFC 扩展 DLL**

   如果希望程序在运行时调用 MFC 库，并且想要在 DLL 和调用应用程序之间共享 MFC 对象，请选择此选项。 如果程序包含多个可执行文件（这些文件都使用 MFC 库），则此选项会降低程序的磁盘和内存要求。 只有 MFC 程序才能调用 DLL 中的函数。 必须重新分发具有此类型项目的 MFC DLL。

## <a name="additional-features"></a>其他功能

选择 MFC DLL 是否应支持自动化以及它是否应支持 Windows 套接字。

- **自动化**

   选择 " **自动化** "，以允许您的程序操作在另一个程序中实现的对象。 选择 " **自动化** " 还会将程序公开给其他自动化客户端。 有关详细信息，请参阅 [自动化](../../mfc/automation.md) 。

- **Windows 套接字**

   选择此选项以指示您的程序支持 Windows 套接字。 Windows 套接字允许编写通过 TCP/IP 网络进行通信的程序。

   创建具有 Windows 套接字支持的 MFC DLL 时， [CWinApp：： InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 初始化对套接字的支持，MFC 头文件 Stdafx.h 包括 AfxSock。

## <a name="see-also"></a>请参阅

[MFC DLL 向导](../../mfc/reference/mfc-dll-wizard.md)<br/>
[创建 MFC DLL 项目](../../mfc/reference/creating-an-mfc-dll-project.md)
