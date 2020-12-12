---
description: 了解详细信息： TN020： ID 命名和编号约定
title: TN020：ID 命名和编号约定
ms.date: 11/04/2016
f1_keywords:
- vc.id
helpviewer_keywords:
- TN020
- resource identifiers, naming and numbering
- resource identifiers
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
ms.openlocfilehash: 85f59e45ec9d4ce748515cf638f4fb4cf33c7d38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215867"
---
# <a name="tn020-id-naming-and-numbering-conventions"></a>TN020：ID 命名和编号约定

此注释描述 MFC 2.0 用于资源、命令、字符串、控件和子窗口的 ID 命名和编号约定。

MFC ID 命名和编号约定旨在满足以下要求：

- 提供在 MFC 库和 Visual C++ 资源编辑器支持的 MFC 应用程序中使用的一致 ID 命名标准。 这使程序员能够更轻松地从其 ID 解释资源的类型和来源。

- 强调某些类型的 Id 之间的强一对多关系。

- 符合已广泛使用的标准，以便在 Windows 中命名 Id。

- 对 ID 编号空间进行分区。 ID 号可由程序员、MFC、Windows 和 Visual C++ 编辑的资源分配。 适当的分区将有助于避免重复的 ID 号。

## <a name="the-id-prefix-naming-convention"></a>ID 前缀命名约定

应用程序中可能会出现几种类型的 Id。 MFC ID 命名约定为不同的资源类型定义不同的前缀。

MFC 使用前缀 "IDR_" 来指示应用于多个资源类型的资源 ID。 例如，对于给定的框架窗口，MFC 使用相同的 "IDR_" 前缀来指示菜单、快捷键、字符串和图标资源。 下表显示了各种前缀及其用法：

|前缀|使用|
|------------|---------|
|IDR_|对于多个资源类型 (主要用于菜单、快捷键和功能区) 。|
|IDD_|例如，对于对话框模板资源 (，IDD_DIALOG1) 。|
|IDC_|适用于游标资源。|
|IDI_|图标资源。|
|IDB_|对于位图资源。|
|IDS_|对于字符串资源。|

在对话资源中，MFC 遵循以下约定：

|前缀或标签|使用|
|---------------------|---------|
|IDOK、IDCANCEL|标准推送按钮 Id。|
|IDC_|对于其他对话框控件。|

"IDC_" 前缀还用于游标。 此命名冲突通常不是问题，因为典型的应用程序将有少量的游标和多个对话框控件。

在菜单资源中，MFC 遵循以下约定：

|前缀|使用|
|------------|---------|
|IDM_|对于不使用 MFC 命令体系结构的菜单项。|
|ID_|对于使用 MFC 命令体系结构的菜单命令。|

遵循 MFC 命令体系结构的命令必须有 ON_COMMAND 命令处理程序，并且可以有 ON_UPDATE_COMMAND_UI 处理程序。 如果这些命令处理程序遵循 MFC 命令体系结构，则它们将正常运行，无论它们是绑定到菜单命令、工具栏按钮还是对话栏按钮。 相同的 "ID_" 前缀还用于显示在程序消息栏上的菜单提示字符串。 应用程序中的大多数菜单项应遵循 MFC 命令约定。 所有标准命令 Id (例如 ID_FILE_NEW) 遵循此约定。

MFC 还使用 "IDP_" 作为一种专用形式的字符串 (而不是 "IDS_" ) 。 带有 "IDP_" 前缀的字符串是提示，也就是说，在消息框中使用的字符串。 "IDP_" 字符串可以包含 "%1" 和 "%2" 作为由程序确定的字符串的占位符。 "IDP_" 字符串通常具有与之关联的帮助主题，而 "IDS_" 字符串则不存在。 "IDP_" 字符串始终本地化，"IDS_" 字符串可能未本地化。

MFC 库还使用 "IDW_" 前缀作为控件 Id 的专用形式 (而不是 "IDC_" ) 。 这些 Id 通过框架类分配给子窗口（如视图和拆分器）。 MFC 实现 Id 以 "AFX_" 为前缀。

## <a name="the-id-numbering-convention"></a>ID-Numbering 约定

下表列出了特定类型的 Id 的有效范围。 某些限制是技术实现限制，而另一些则是一些约定，旨在防止 Id 与 Windows 预定义 Id 或 MFC 默认实现发生冲突。

强烈建议您在建议范围内定义所有 Id。 这些范围的下限为1，因为未使用0。 建议使用常见约定，并使用100或101作为第一个 ID。

|前缀|资源类型|有效范围|
|------------|-------------------|-----------------|
|IDR_|multiple|1到0x6FFF|
|IDD_|对话框模板|1到0x6FFF|
|IDC_、IDI_ IDB_|光标、图标、位图|1到0x6FFF|
|IDS_，IDP_|常规字符串|1到0x7FFF|
|ID_|命令|0x8000 到0xDFFF|
|IDC_|controls|8到0xDFFF|

这些范围限制的原因：

- 按照约定，不使用 ID 值0。

- Windows 实现限制将 true 资源 Id 限制为小于或等于0x7FFF。

- MFC 的内部框架保留以下范围：

  - 0x7000 到 0x7FFF (参阅 afxres.h) 

  - 0xE000 到 0xEFFF (参阅 afxres.h) 

  - 16000到 18000 (参阅 afxribbonres) 

  这些范围在未来的 MFC 实现中可能会更改。

- 几个 Windows 系统命令使用0xF000 到0xFFFF 范围内的。

- 1到7的控件 Id 是为标准控件（例如 IDOK 和 IDCANCEL）保留的。

- 字符串的0x8000 到0xFFFF 的范围是为命令的菜单提示保留的。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
