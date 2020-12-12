---
description: 了解详细信息：用于创建 OLE 应用程序的操作顺序
title: 用于创建 OLE 应用程序的操作顺序
ms.date: 11/04/2016
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
ms.openlocfilehash: 2bce49d569c6d3def536cbe9386cafbe08ccdbfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217557"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>用于创建 OLE 应用程序的操作顺序

下表显示了在创建 OLE 链接和嵌入应用程序时的角色和框架的角色。 它们表示可用的选项，而不是要执行的一系列步骤。

### <a name="creating-ole-applications"></a>创建 OLE 应用程序

|任务|您执行的操作|框架执行的操作|
|----------|------------|------------------------|
|创建 COM 组件。|运行 MFC 应用程序向导。 在 "**复合文档支持**" 选项卡中选择 "**全服务器**" 或 "**小型服务器**"。|框架将生成启用了 COM 组件功能的主干应用程序。 所有 COM 功能都可传输到现有应用程序，只需要稍作修改。|
|从头开始创建容器应用程序。|运行 MFC 应用程序向导。 在 "**复合文档支持**" 选项卡中选择 "**容器**"。使用类视图，请参阅源代码编辑器。 填写 COM 处理函数的代码。|框架生成可插入 com 组件 (server) 应用程序创建的 COM 对象的框架应用程序。|
|从头开始创建支持自动化的应用程序。|运行 MFC 应用程序向导。 从 "**高级功能**" 选项卡中选择 "**自动化**"。使用类视图公开应用程序中的方法和属性以实现自动化。|框架生成可由其他应用程序激活和自动化的主干应用程序。|

## <a name="see-also"></a>请参阅

[基于框架生成](../mfc/building-on-the-framework.md)<br/>
[用于生成 MFC 应用程序的操作序列](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[用于创建 ActiveX 控件的操作顺序](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[用于创建数据库应用程序的操作顺序](../mfc/sequence-of-operations-for-creating-database-applications.md)
