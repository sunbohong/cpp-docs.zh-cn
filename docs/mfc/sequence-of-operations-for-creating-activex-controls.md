---
description: 了解详细信息：用于创建 ActiveX 控件的操作顺序
title: 用于创建 ActiveX 控件的操作顺序
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
ms.openlocfilehash: 15b81716f5feee4dfd4d0ebf47ee4d0d648c4536
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217623"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>用于创建 ActiveX 控件的操作顺序

下表显示了在创建 ActiveX 控件 (以前称为 OLE 控件) 的角色和框架的角色。

### <a name="creating-activex-controls"></a>创建 ActiveX 控件

|任务|您执行的操作|框架执行的操作|
|----------|------------|------------------------|
|创建 ActiveX 控件框架。|运行 MFC ActiveX 控件向导来创建控件。 在选项页中指定您需要的选项。 选项包括 "项目"、"授权"、"子类" 和 "关于" 框方法中的控件的类型和名称。|MFC ActiveX 控件向导为具有基本功能的 ActiveX 控件创建文件，包括应用程序、控件和属性页或页的源文件;资源文件;项目文件;另外，还为您的规范量身打造。|
|查看控件和 ActiveX 控件向导提供的内容，而无需添加您自己的代码行。|生成 ActiveX 控件，并通过 Internet Explorer 或 [TSTCON 示例](../overview/visual-cpp-samples.md)对其进行测试。|运行控件可以调整大小和移动。 如果选择了可调用) ，它还会 (**"关于" 框** 方法。|
|实现控件的方法和属性。|通过添加成员函数来实现控件特定的方法和属性，以便为控件的数据提供公开的接口。 添加成员变量以保存数据结构，并使用事件处理程序在确定时激发事件。|该框架已经定义了一个映射，以支持该控件的事件、属性和方法，使您能够专注于如何实现属性和方法。 默认属性页是可查看的，并提供了默认的关于 Box 方法。|
|构造控件的属性页。|使用 Visual C++ 资源编辑器以直观方式编辑控件的属性页界面：<br /><br />-创建其他属性页。<br />-创建和编辑位图、图标和光标。<br /><br /> 您还可以在对话框编辑器中测试)  (的属性页。|MFC 应用程序向导创建的默认资源文件提供了很多您需要的资源。 利用 Visual C++，您可以轻松直观地编辑现有资源和添加新资源。|
|测试控件的事件、方法和属性。|重新生成控件并使用测试容器测试您的处理程序是否正常工作。|可以调用控件的方法，并通过属性页接口或测试容器来操作其属性。 此外，使用 "测试容器" 跟踪从控件引发的事件和控件的容器接收的通知。|

## <a name="see-also"></a>请参阅

[基于框架生成](../mfc/building-on-the-framework.md)<br/>
[用于生成 MFC 应用程序的操作序列](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[用于创建 OLE 应用程序的操作顺序](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[用于创建数据库应用程序的操作顺序](../mfc/sequence-of-operations-for-creating-database-applications.md)
