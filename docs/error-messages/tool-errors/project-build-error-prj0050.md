---
description: 了解详细信息：项目生成错误 PRJ0050
title: 项目生成错误 PRJ0050
ms.date: 11/04/2016
f1_keywords:
- PRJ0050
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
ms.openlocfilehash: 07a4df24f48a61e29214431840649566716bbac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240801"
---
# <a name="project-build-error-prj0050"></a>项目生成错误 PRJ0050

未能注册输出。 请确保您具有适当的权限来修改注册表。

Visual C++ 生成系统无法注册生成 (dll 或 .exe) 的输出。 需要以管理员身份登录才能修改注册表。

如果要生成 .dll，可以尝试使用 regsvr32.exe 手动注册 .dll，这应显示有关生成失败的原因的信息。

如果未生成 .dll，请查看导致错误的命令的生成日志。
