---
description: 了解详细信息：项目生成错误 PRJ0016
title: 项目生成错误 PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: a34783e46bbe4c7b9979fe9b3d200cde4c228885
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343829"
---
# <a name="project-build-error-prj0016"></a>项目生成错误 PRJ0016

用户的安全设置阻止创建进程。 这些设置是生成所必需的。

你以无权使用进程创建进程的用户身份登录。 必须更改此用户帐户的权限级别，或与帐户管理员联系。

如果设置了以下注册表项，也会发生此错误：

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

若要解决此错误，请删除 RestrictRun 项。 如果需要此注册表项，请将 **vcspawn.exe** 追加到项中的项列表。

导致此错误的另一个原因是，策略设置不会在注册表项下包含 VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun 作为此用户帐户的允许的窗口程序。

有关其他信息，请参阅 "仅运行允许的 Windows 应用程序" 部分中的 " [坚持使用系统策略设置](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)"。
