---
description: 了解详细信息：向对象添加连接点
title: 将连接点添加到对象
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
ms.openlocfilehash: 7d8274ab37cef28a58666852aad24db7d945d26e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166234"
---
# <a name="adding-connection-points-to-an-object"></a>将连接点添加到对象

[ATL 教程](../atl/active-template-library-atl-tutorial.md)演示了如何创建一个控件，该控件支持连接点、如何添加事件，以及如何实现连接点。 ATL 用 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 类实现连接点。

若要实现连接点，你有两种选择：

- 通过向控件或对象添加连接点实现自己的传出事件源。

- 重新使用在其他类型库中定义的连接点接口。

在任一情况下，"实现连接点向导" 使用类型库来完成工作。

### <a name="to-add-a-connection-point-to-a-control-or-object"></a>向控件或对象添加连接点

1. 在 .idl 文件的库块中定义调度接口。 如果在通过 ATL 控件向导创建控件时启用了对连接点的支持，则已创建调度接口。 如果在创建控件时未启用对连接点的支持，则必须手动将调度接口添加到 .idl 文件中。 下面是一个调度接口的示例。 传出接口不需要为调度接口，但许多脚本语言（如 VBScript 和 JScript）需要此操作，因此，此示例使用两个调度接口：

   [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]

   使用 uuidgen.exe 或 guidgen.exe 实用工具生成 GUID。

2. 在 `[default,source]` 项目的 .idl 文件中的对象的 coclass 中添加调度接口作为接口。 同样，如果你在创建控件时启用了对连接点的支持，则 ATL 控件向导将创建 "" `[default,source` 项。 若要手动添加此项，请用粗体添加行：

   [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]

   有关示例，请参阅 [Circ](../overview/visual-cpp-samples.md) ATL 示例中的 .idl 文件。

3. 使用类视图将方法和属性添加到事件接口。 右键单击 "类视图中的类，指向快捷菜单上的" **添加** "，然后单击" **添加连接点**"。

4. 在 "实现连接点向导" 的 " **源接口** " 列表框中，选择 " **项目的接口**"。 如果为控件选择接口并按 **"确定"**，则会执行以下操作：

   - 生成包含事件代理类的标头文件，该事件代理类实现将发出事件的传出调用的代码。

   - 将条目添加到连接点映射。

   您还将看到您的计算机上所有类型库的列表。 如果要实现在其他类型库中找到的完全相同的输出接口，则只能使用这些其他类型库之一来定义连接点。

### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>重用其他类型库中定义的连接点接口

1. 在类视图中，右键单击实现 **BEGIN_COM_MAP** 宏的类，指向快捷菜单上的 " **添加** "，然后单击 " **添加连接点**"。

2. 在实现连接点向导中，选择类型库和类型库中的接口，然后单击 " **添加**"。

3. 编辑 .idl 文件，以执行以下任一操作：

   - 为正在使用其事件源的对象复制 .idl 文件中的调度接口。

   - 对该类型库使用 **importlib** 指令。

## <a name="see-also"></a>请参阅

[连接点](../atl/atl-connection-points.md)
