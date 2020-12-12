---
description: 了解详细信息： ATL 项目中的 COM + 1.0 支持
title: ATL 项目中的 COM + 1.0 支持
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.MTS
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
ms.openlocfilehash: 8e196bccf25667da28532248765e47906fdcee97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141279"
---
# <a name="com-10-support-in-atl-projects"></a>ATL 项目中的 COM + 1.0 支持

您可以使用 [ATL 项目向导](../../atl/reference/creating-an-atl-project.md) 创建对 com + 1.0 组件的基本支持的项目。

COM + 1.0 设计用于开发基于组件的分布式应用程序。 它还提供了用于部署和管理这些应用程序的运行时基础结构。

如果选择 " **支持 COM + 1.0** " 复选框，则向导将修改链接步骤中的生成脚本。 具体而言，COM + 1.0 项目链接到以下库：

- comsvcs

- Mtxguid

如果选择 " **支持 COM + 1.0** " 复选框，则还可以选择 " **支持组件注册** 器"。 组件注册机构允许 COM + 1.0 对象获取组件列表、注册组件，或将组件单独注册 () 。

## <a name="see-also"></a>请参阅

[ATL COM 对象的基本知识](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[用 ATL 和 C Run-Time 代码编程](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[默认 ATL 项目配置](../../atl/reference/default-atl-project-configurations.md)
