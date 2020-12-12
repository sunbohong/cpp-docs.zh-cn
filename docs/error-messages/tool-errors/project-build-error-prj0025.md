---
description: 了解详细信息：项目生成错误 PRJ0025
title: 项目生成错误 PRJ0025
ms.date: 08/27/2018
f1_keywords:
- PRJ0025
helpviewer_keywords:
- PRJ0025
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
ms.openlocfilehash: 9d7c17b9dcf8b37d14285cfd05bc92a8598f9b19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291384"
---
# <a name="project-build-error-prj0025"></a>项目生成错误 PRJ0025

> 批处理文件 "*file*" 包含无法翻译成用户的 ANSI 代码页的 Unicode 内容。
>
> *文件的 UNICODE 内容*

项目系统在无法正确转换为用户的当前 ANSI 代码页的自定义生成规则或生成事件中找到了 Unicode 内容。

此错误的解决方法是更新生成规则或生成事件的内容以使用 ANSI 或在计算机上安装代码页，并将其设置为系统默认值。

有关自定义生成步骤和生成事件的详细信息，请参阅 [了解自定义生成步骤和生成事件](../../build/understanding-custom-build-steps-and-build-events.md)。
