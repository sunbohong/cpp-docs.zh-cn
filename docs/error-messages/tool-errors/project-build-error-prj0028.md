---
description: 了解详细信息：项目生成错误 PRJ0028
title: 项目生成错误 PRJ0028
ms.date: 11/04/2016
f1_keywords:
- PRJ0028
helpviewer_keywords:
- PRJ0028
ms.assetid: 0a6e0da7-cb3d-40b6-81a6-6196a9c2526b
ms.openlocfilehash: 83c910aba082ab23255fc4ff03c0e19cadf3af7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291267"
---
# <a name="project-build-error-prj0028"></a>项目生成错误 PRJ0028

临时文件 "file" 包含无法翻译成用户的 ANSI 代码页的 Unicode 内容。

使用/MIDL 指定了一个值 [ (指定 MIDL 命令行选项) ](../../build/reference/midl-specify-midl-command-line-options.md) 链接器选项，系统代码页无法对其进行解析。

在输入代码页 (指定 MIDL 命令时使用的代码页) 必须与系统代码页相同。
