---
description: 了解详细信息：添加 ATL 简单对象
title: 添加 ATL 简单对象
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.adding.atl
helpviewer_keywords:
- ATL projects, adding objects
- objects [ATL]
- ATL, simple objects
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
ms.openlocfilehash: 9e354f7d361c64f20657190bc53696f9878fa134
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158929"
---
# <a name="adding-an-atl-simple-object"></a>添加 ATL 简单对象

若要向项目添加 ATL (活动模板库) 对象，则必须已将项目创建为 ATL 应用程序或包含 ATL 支持的 MFC 应用程序。 您可以使用 [Atl 项目向导](../../atl/reference/atl-project-wizard.md) 创建 atl 应用程序，或 [将 atl 对象添加到 mfc 应用](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) 程序，以便为 MFC 应用程序实现 atl 支持。

您可以在首次创建新的 ATL 对象时为新的 ATL 对象定义 COM 接口，或在以后使用 **类视图** 快捷菜单中的 "[实现接口](../../ide/implementing-an-interface-visual-cpp.md#implement-interface-wizard)" 命令来添加它们。

## <a name="to-add-an-atl-simple-object-to-your-atl-com-project"></a>向 ATL COM 项目添加 ATL 简单对象

1. 在 " **解决方案资源管理器** " 或 " [类视图](/visualstudio/ide/viewing-the-structure-of-code)中，右键单击要向其添加 ATL 简单对象的项目的名称。

1. 在快捷菜单中，单击 " **添加**"，然后单击 " **添加类**"。

1. 在 " [添加类](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) " 对话框的 " **模板** " 窗格中，单击 " **atl 简单对象**"，然后单击 " **打开** " 以显示 " [atl 简单对象向导](../../atl/reference/atl-simple-object-wizard.md)"。

1. 在 **ATL 简单对象** 向导的 "[选项](../../atl/reference/options-atl-simple-object-wizard.md)" 页上设置项目的附加选项。

1. 单击 " **完成** "，将对象添加到项目。

## <a name="see-also"></a>请参阅

[添加类](../../ide/adding-a-class-visual-cpp.md)<br/>
[在 ATL 项目中添加新接口](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[向对象添加连接点](../../atl/adding-connection-points-to-an-object.md)<br/>
[添加方法](../../ide/adding-a-method-visual-cpp.md)<br/>
[MFC 类](../../mfc/reference/adding-an-mfc-class.md)<br/>
[添加一般 C++ 类](../../ide/adding-a-generic-cpp-class.md)
