---
description: 了解详细信息：为提供程序创建项目
title: 为提供程序创建项目
ms.date: 10/22/2018
helpviewer_keywords:
- ATL projects, creating
- OLE DB providers, projects
- projects [C++], creating
ms.assetid: 076a75de-1d4b-486a-bcf8-9c0f6b049fa2
ms.openlocfilehash: 9094e4bfc57838425793fac0c009ed70259dcb3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323241"
---
# <a name="creating-a-project-for-the-provider"></a>为提供程序创建项目

## <a name="to-create-a-project-in-which-the-ole-db-provider-will-reside"></a>创建一个将驻留 OLE DB 提供程序的项目

1. 在“文件”菜单上，单击“新建”，然后单击“项目”。

   此时将出现“新建项目”  对话框。

1. 在 "**项目类型**" 窗格中，单击 "**已安装** 的  >  **Visual C++**  >  **MFC/ATL** " 文件夹。 在 " **模板** " 窗格中单击 " **ATL 项目**"。

    > [!NOTE]
    > 在 Visual Studio 的早期版本中，在 "**已安装** 的  >  **模板**  >  **Visual C++**  >  **ATL**" 下找到项目类型。

1. 在 " **名称** " 框中，输入项目的名称，然后单击 **"确定"**。

   此时将显示 " **ATL 项目" 向导** 。

1. 在 **ATL 项目向导** 中，为 **应用程序类型** 选择 **动态链接库 (DLL)** 。

1. 单击“完成”。

## <a name="see-also"></a>请参阅

[创建 OLE DB 提供程序](../../data/oledb/creating-an-ole-db-provider.md)
