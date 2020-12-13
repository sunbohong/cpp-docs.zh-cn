---
description: 了解详细信息：在框架上生成
title: 基于框架生成
ms.date: 11/04/2016
helpviewer_keywords:
- application-specific classes [MFC]
- application framework [MFC], building applications
- applications [MFC]
- MFC, application development
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
ms.openlocfilehash: dd9423bb8cf80463631d6a39212db42ab94a67ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339782"
---
# <a name="building-on-the-framework"></a>基于框架生成

在使用 MFC 框架配置应用程序时，您的角色是提供应用程序特定的源代码，并通过定义它们所响应的消息和命令来连接这些组件。 你使用 c + + 语言和标准 c + + 技术从类库提供的类派生你自己的应用程序特定的类，并重写并增加基类的行为。

在 "相关主题" 中，下表描述了通常应遵循的一般操作顺序，以及与框架的责任：

- [使用框架生成应用程序的顺序](sequence-of-operations-for-building-mfc-applications.md)

- [用于创建 OLE 应用程序的操作顺序](sequence-of-operations-for-creating-ole-applications.md)

- [用于创建 ActiveX 控件的操作顺序](sequence-of-operations-for-creating-activex-controls.md)

- [用于创建数据库应用程序的操作顺序](sequence-of-operations-for-creating-database-applications.md)

在大多数情况下，你可以按照这些表中所述的步骤来创建 MFC 应用程序，但其中一些步骤是替代选项。 例如，大多数应用程序使用几种类型的视图类，可使用多种类型。

## <a name="see-also"></a>请参阅

[常规 MFC 主题](general-mfc-topics.md)
