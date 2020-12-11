---
description: 了解详细信息：在 ATL 项目中添加新接口
title: 在 ATL 项目中添加新接口
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.interface
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
ms.openlocfilehash: 7db5cd5f613985caf22253736ae691f3af9240ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159136"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>在 ATL 项目中添加新接口

向对象或控件添加接口时，将为该接口中的每个方法创建用作存根函数。 在您的对象或控件中，您只能添加当前在现有类型库中找到的接口。 此外，添加接口的类必须实现 [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) 宏，如果项目是特性化的，则必须具有 `coclass` 特性。

可以通过以下两种方式之一向控件添加新接口：在类视图中手动或使用代码向导。

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>在类视图中使用代码向导向现有对象或控件添加接口

1. 在 [类视图](/visualstudio/ide/viewing-the-structure-of-code)中，右键单击控件的类名。 例如，完全控制或复合控件或在其头文件中实现 BEGIN_COM_MAP 宏的任何其他控件类。

1. 在快捷菜单上，单击 " **添加**"，然后单击 " **实现接口**"。

1. 选择要在 [实现接口向导](../../ide/implementing-an-interface-visual-cpp.md#implement-interface-wizard)中实现的接口。 如果接口不存在于任何可用的类型库中，则必须手动将其添加到 .idl 文件中。

## <a name="to-add-a-new-interface-manually"></a>手动添加新接口

1. 将新接口的定义添加到 .idl 文件中。

1. 从接口派生对象或控件。

1. 为接口创建新的 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) ，如果项目是特性化的，则添加 `coclass` 特性。

1. 在接口上实现方法。

## <a name="see-also"></a>请参阅

[ATL 项目向导](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio 中的 C++ 项目类型](../../build/reference/visual-cpp-project-types.md)<br/>
[用 ATL 和 C Run-Time 代码编程](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM 对象的基本知识](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[默认 ATL 项目配置](../../atl/reference/default-atl-project-configurations.md)
