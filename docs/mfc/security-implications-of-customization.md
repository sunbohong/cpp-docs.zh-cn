---
description: 了解详细信息：自定义的安全隐患
title: 自定义对安全有何影响
ms.date: 11/04/2016
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
ms.openlocfilehash: 64a1029dd3486e3cd653f5e692aa1a14ba6f82b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217752"
---
# <a name="security-implications-of-customization"></a>自定义对安全有何影响

本主题讨论了 MFC 中潜在的安全漏洞。

## <a name="potential-security-weakness"></a>潜在的安全漏洞

MFC 允许用户自定义应用程序用户界面的外观，例如，图标和按钮的外观。 MFC 还支持能够让用户执行 shell 命令的用户定义的工具。 由于应用程序的自定义设置保存在注册表的用户配置文件中，因此可能会导致安全漏洞。 任何访问该注册表的人员都可以编辑这些设置并更改应用程序的外观或行为。 例如，计算机的管理员可以通过促使用户的应用程序执行任意程序（甚至从网络共享中）来模拟用户。

## <a name="workarounds"></a>工作区

我们建议采用以下三种方法中的任一方法来关闭注册表中的漏洞：

- 对存储在注册表中的数据进行加密。

- 将数据存储在安全文件而不是注册表中。

   若要实现这两种方法中的任意一种，请从 [CSettingsStore 类](../mfc/reference/csettingsstore-class.md) 派生一个类，并重写其方法，以便在注册表外部实现加密或存储。

- 还可以在应用程序中禁用自定义。

## <a name="see-also"></a>请参阅

[MFC 自定义](../mfc/customization-for-mfc.md)
