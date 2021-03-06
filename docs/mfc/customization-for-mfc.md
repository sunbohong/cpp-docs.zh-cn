---
description: 了解详细信息： MFC 自定义
title: MFC 自定义
ms.date: 11/04/2016
helpviewer_keywords:
- customizations, MFC Extensions
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
ms.openlocfilehash: 50df32d4743381e1212eae53b695e2355bc8d0e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309402"
---
# <a name="customization-for-mfc"></a>MFC 自定义

本主题提供了有关自定义 MFC 应用程序的提示。

## <a name="general-customizations"></a>常规自定义

您可以将应用程序状态保存并加载到注册表。 如果启用此选项，则应用程序将从注册表加载其初始状态。 如果更改应用程序的初始停靠布局，则必须清除应用程序的注册表数据。 否则，注册表中的数据将覆盖您对初始布局的所有更改。

## <a name="class-specific-customizations"></a>特定于类的自定义

可以在下列主题中找到其他自定义提示：

- [CBasePane 类](reference/cbasepane-class.md)

- [CDockablePane 类](reference/cdockablepane-class.md)

- [CDockingManager 类](reference/cdockingmanager-class.md)

- [CMFCBaseTabCtrl 类](reference/cmfcbasetabctrl-class.md)

## <a name="additional-customization-tips"></a>其他自定义提示

[键盘和鼠标自定义](keyboard-and-mouse-customization.md)

[用户定义的工具](user-defined-tools.md)

## <a name="see-also"></a>请参阅

[MFC 桌面应用程序](mfc-desktop-applications.md)<br/>
[自定义的安全隐患](security-implications-of-customization.md)
