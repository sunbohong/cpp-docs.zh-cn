---
description: 了解详细信息：应用程序设置，ATL 项目向导
title: 应用程序设置，ATL 项目向导
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.atl.com.appset
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
ms.openlocfilehash: 7805fcb8760035ac232a36a42a1cf34273ee42a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158934"
---
# <a name="application-settings-atl-project-wizard"></a>应用程序设置，ATL 项目向导

使用 ATL 项目向导的 " **应用程序设置** " 页，可以设计基本功能并将其添加到新的 ATL 项目。

## <a name="server-type"></a>服务器类型

选择以下三种服务器类型之一：

- **动态链接库 (DLL)**

   选择此项可创建进程内服务器。

- **可执行文件 (EXE)**

   选择此项可创建本地进程外服务器。 此选项不允许对 MFC 或 COM + 1.0 的支持。 它不允许合并代理/存根代码。

- **Service (EXE)**

   选择此项可在 Windows 启动时创建在后台运行的 Windows 应用程序。 此选项不允许对 MFC 或 COM + 1.0 的支持或不允许合并代理/存根代码。

## <a name="additional-options"></a>其他选项

> [!NOTE]
> 所有其他选项仅适用于 DLL 项目。

- **允许合并代理/存根代码**

   如果需要封送处理接口，请选中 " **允许合并代理/存根代码** " 复选框。 此选项将 MIDL 生成的代理和存根代码放在与服务器相同的可执行文件中。

- **支持 MFC**

   选择此对象可指定对象包含 MFC 支持。 此选项将您的项目链接到 MFC 库，以便您可以访问它们包含的任何类和函数。

- **支持 COM + 1。0**

   选择此项目可以修改项目生成设置以支持 COM + 1.0 组件。 除了库的标准列表，向导还添加了 COM + 1.0 组件特定的库 comsvcs

   此外，在启动应用程序时，mtxex.dll 会延迟加载到主机系统上。

- **支持组件注册机构**

   如果 ATL 项目包含对 COM + 1.0 组件的支持，则可以设置此选项。 组件注册机构允许 COM + 1.0 对象获取组件列表、注册组件，或将组件单独注册 () 。

## <a name="see-also"></a>请参阅

[ATL 项目向导](../../atl/reference/atl-project-wizard.md)<br/>
[创建 ATL 项目](../../atl/reference/creating-an-atl-project.md)<br/>
[默认 ATL 项目配置](../../atl/reference/default-atl-project-configurations.md)
