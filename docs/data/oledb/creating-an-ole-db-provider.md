---
description: 了解详细信息：创建 OLE DB 提供程序
title: 创建 OLE DB 提供程序
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
ms.openlocfilehash: 69dc9311a79f2739636633b2d268343a92d2dac9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287796"
---
# <a name="creating-an-ole-db-provider"></a>创建 OLE DB 提供程序

创建 OLE DB 提供程序的建议方法是使用向导创建 ATL COM 项目和提供程序，然后使用 OLE DB 模板修改这些文件。 自定义提供程序时，可以注释掉不需要的属性并添加可选接口。

基本步骤如下所示：

1. 使用 **atl 项目向导** 创建基本项目文件，使用 **atl oledb 提供程序向导** 创建提供程序， (在 "添加新项") 的 "**已安装** 的 Visual C++ ATL" 文件夹中选择 " **atl oledb 提供程序**"  >    >   。 

   > [!NOTE]
   > 添加 **ATL OLEDB 提供程序** 之前，该项目必须包含 MFC 支持。

1. 修改 `Execute` [CCustomRowset (CustomRS) ](cmyproviderrowset-myproviderrs-h.md)中方法中的代码。 有关示例，请参阅 [将字符串读入 OLE DB 提供程序](../../data/oledb/reading-strings-into-the-ole-db-provider.md)。

1. 编辑 [CustomDS](cmyprovidersource-myproviderds-h.md)、 [CustomSess](cmyprovidersession-myprovidersess-h.md)和 [CustomRS](cmyproviderrowset-myproviderrs-h.md)中的属性映射。 向导将创建包含提供程序可能实现的所有属性的属性映射。 浏览属性 "映射"，删除或注释掉提供程序不需要支持的属性。

1. 更新 PROVIDER_COLUMN_MAP，可在 [CCustomRowset (CustomRS) ](cmyproviderrowset-myproviderrs-h.md)中找到。 有关示例，请参阅 [在 OLE DB 提供程序中存储字符串](../../data/oledb/storing-strings-in-the-ole-db-provider.md)。

1. 准备好测试提供程序时，可以通过尝试在提供程序枚举中查找提供程序对其进行测试。 有关在枚举中查找提供程序的测试代码的示例，请参阅 [CATDB](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) 和 [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) 示例或 [实现简单使用者](../../data/oledb/implementing-a-simple-consumer.md)中的示例。

1. 添加所需的任何其他接口。 有关示例，请参阅 [增强简单的 Read-Only 提供程序](../../data/oledb/enhancing-the-simple-read-only-provider.md)。

   > [!NOTE]
   > 默认情况下，向导将生成 OLE DB 级别0兼容的代码。 若要确保应用程序保持级别0符合，请不要从代码中删除任何向导生成的接口。

## <a name="see-also"></a>请参阅

[CatDB 示例：数据源架构浏览器](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[DBViewer 示例：数据库浏览器](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
