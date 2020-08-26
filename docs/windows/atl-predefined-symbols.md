---
title: ATL 预定义的符号
ms.date: 02/14/2019
helpviewer_keywords:
- symbols [C++], ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
ms.openlocfilehash: 8134f334b0143a360fd3e02c04bca7a65ce67ce0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836382"
---
# <a name="atl-predefined-symbols"></a>ATL 预定义的符号

这些符号在 ATL 标头文件中定义，但它们支持标准的 Windows 应用程序函数和操作。 这些符号主要与对话框一起使用。

在 [对话框编辑器](dialog-editor.md)中处理对话框和控件时，这些符号会出现在与公共控件关联的 [属性窗口](/visualstudio/ide/reference/properties-window) 中。 例如，如果您的对话框有 " **取消** " 按钮，则该命令将与 " **属性** " 窗口中的符号 IDCANCEL 相关联。

|名称|说明|
|-|-|
|IDABORT| (控制) "对话框中的" 中止 "按钮|
|IDC_STATIC| (控件) 静态控件|
|IDCANCEL| (控制) "对话框中的" 取消 "按钮|
|IDIGNORE| (控制) "对话框中的" 忽略 "按钮|
|IDNO| (控件) 对话框，无按钮|
|IDOK| (控制) "对话框中的" 确定 "按钮|
|IDR_ACCELERATOR1| (资源) 快捷键对应表|
|IDRETRY| (控制) "对话框中的" 重试 "按钮|
|IDS_PROJNAME| (字符串) 当前应用程序名称|
|IDYES| (控件) 对话框，"是" 按钮|

## <a name="requirements"></a>要求

ATL

## <a name="see-also"></a>另请参阅

[预定义的符号 Id](predefined-symbol-ids.md)<br/>
[MFC 预定义符号](mfc-predefined-symbols.md)<br/>
[Win32 预定义符号](win32-predefined-symbols.md)<br/>
