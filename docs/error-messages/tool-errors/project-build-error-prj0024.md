---
description: 了解详细信息：项目生成错误 PRJ0024
title: 项目生成错误 PRJ0024
ms.date: 08/27/2018
f1_keywords:
- PRJ0024
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
ms.openlocfilehash: e42df62181d02cf8d4696cc4f48afcec52cd4d76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150457"
---
# <a name="project-build-error-prj0024"></a>项目生成错误 PRJ0024

> Unicode 路径 "*path*" 未能转换为用户的 ANSI 代码页。

*path* 是路径字符串的原始 Unicode 版本。 如果有一个 Unicode 路径无法直接翻译为当前系统代码页的 ANSI 路径，则可能出现此错误。

如果正在使用的代码页不在计算机上，则可能会发生此错误。

此错误的解决方法是更新路径以使用 ANSI 文本或在计算机上安装代码页，并将其设置为系统默认值。
