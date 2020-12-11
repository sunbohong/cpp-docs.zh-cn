---
description: 了解详细信息： ATL 对话框向导
title: ATL 对话框向导
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
ms.openlocfilehash: 2fc110f12399c0c855cb98a9d7e505180bef7b0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158876"
---
# <a name="atl-dialog-wizard"></a>ATL 对话框向导

此向导将向项目中插入一个从 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)派生的 ATL 对话框对象。 派生自的对话框 `CAxDialogImpl` 可承载 ActiveX 控件。

向导使用默认的 **"确定" 和 "** **取消** " 按钮创建对话框资源。 可以在资源视图中使用 [对话框编辑器](../../windows/dialog-editor.md) 来编辑对话框资源和添加 ActiveX 控件。

向导将向标头文件中插入 [消息映射](../../atl/message-maps-atl.md) 和用于处理默认 click 事件的声明。 有关 ATL 对话框的详细信息，请参阅 [实现对话框](../../atl/implementing-a-dialog-box.md) 。

- **短名称**

   设置 ATL 对话框对象的缩写名称。 您提供的名称将确定类名称和文件 ( .cpp 和 .h) 名称，除非单独更改这些字段。

- **类**

   设置要创建的类的名称。 此名称以你在“短名称”中提供的名称为依据，跟在典型的类名前缀“C”后面。

- **.h 文件**

   为新项目的类的头文件设置名称。 默认情况下，此名称以你在“短名称”中提供的名称为依据。 单击省略号按钮以将该文件名保存至所选择的位置，或追加到某个现有文件的类声明中。 如果选择现有文件，则向导在你单击“完成”之前都不会将其保存至所选位置。

   向导不会覆盖文件。 如果选择现有文件的名称，当你单击“完成”时，向导会询问你是否要将该类声明追加至文件的内容中。 单击“是”，则追加该文件；单击“否”，则返回至向导并指定另一个文件名。

- **.cpp 文件**

   为新项目的类的实现文件设置名称。 默认情况下，此名称以你在“短名称”中提供的名称为依据。 单击省略号按钮以将文件名保存到所选位置。 向导在你单击“完成”之前不会将该文件保存到所选位置。

   向导不会覆盖文件。 如果选择现有文件的名称，当你单击“完成”时，向导会询问你是否要将该类实现追加至文件的内容中。 单击“是”，则追加该文件；单击“否”，则返回至向导并指定另一个文件名。

## <a name="see-also"></a>请参阅

[ATL 对话框](../../atl/reference/adding-an-atl-dialog-box.md)
