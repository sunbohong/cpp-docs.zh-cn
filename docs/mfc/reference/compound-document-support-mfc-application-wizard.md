---
description: 了解详细信息： MFC 应用程序向导的复合文档支持
title: MFC 应用程序向导的复合文档支持
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.compdoc
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
ms.openlocfilehash: 5ccd95812c7b8a4379528b4c784a3d7ca09f538f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331366"
---
# <a name="compound-document-support-mfc-application-wizard"></a>MFC 应用程序向导的复合文档支持

在 MFC 应用程序向导的此页中，向应用程序提供复合和活动文档支持的级别。 您的应用程序必须支持文档/视图体系结构以支持复合文档和文档模板。

默认情况下，应用程序不包含复合文档支持。 如果接受此默认值，您的应用程序将不支持活动文档或复合文件。

- **复合文档支持**

  确定应用程序是提供容器支持、服务器支持还是同时提供两者。 有关此方面的详细信息，请参阅：

  - [容器：实现容器](../../mfc/containers-implementing-a-container.md)

  - [服务器：实现服务器](../../mfc/servers-implementing-a-server.md)

  |选项|说明|
  |------------|-----------------|
  |无|指示不支持 (OLE) 的对象链接和嵌入。 默认情况下，应用程序向导创建不支持 ActiveX 的应用程序。|
  |**容器**|包含链接的和嵌入的对象。|
  |**迷你服务器**|指示应用程序可创建和管理复合文档对象。 请注意，小型服务器不能独立运行，只支持嵌入项。|
  |**完全服务器**|指示应用程序可创建和管理复合文档对象。 完全服务器可以独立运行，同时支持链接项和嵌入项。|
  |**容器/完全服务器**|指示应用程序可以同时为容器和服务器。 容器是一种应用程序，可将嵌入或链接的项合并到其自己的文档中。 服务器是一种应用程序，可以创建自动化项以供容器应用程序使用。|

- **其他选项**

  指示应用程序是否支持活动文档。 有关此功能的详细信息，请参阅 [活动文档](../../mfc/active-documents.md) 。

  |选项|描述|
  |------------|-----------------|
  |**活动文档服务器**|指示应用程序可创建和管理活动文档。 如果选择此选项，则必须在向导的 "[文档模板字符串](../../mfc/reference/document-template-strings-mfc-application-wizard.md)" 页的 "**文件扩展名**" 框中为活动文档服务器指定文件扩展名。 有关详细信息，请参阅 [活动文档服务器](../../mfc/active-document-servers.md) 。|
  |**活动文档容器**|指示应用程序可以在其框架内包含活动文档。 例如，活动文档可能包括 Internet Explorer 文档或 Microsoft Word 文件或 Excel 电子表格等 Office 文档。 有关详细信息，请参阅 [活动文档包容](../../mfc/active-document-containment.md) 。|
  |**支持复合文件**|不使用复合文件格式序列化容器应用程序的文档。 此选项强制将包含对象的整个文件加载到内存中。 单个对象的增量保存功能不可用。 如果更改了某个对象并随后将其保存，则会保存该文件中的所有对象。|

## <a name="see-also"></a>请参阅

[MFC 应用程序向导](../../mfc/reference/mfc-application-wizard.md)
