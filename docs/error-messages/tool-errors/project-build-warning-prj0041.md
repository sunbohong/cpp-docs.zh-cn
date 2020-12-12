---
description: 了解详细信息：项目生成警告 PRJ0041
title: 项目生成警告 PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: dc6b36e052d3402f047257a4bf0035d7ec30f92a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206443"
---
# <a name="project-build-warning-prj0041"></a>项目生成警告 PRJ0041

找不到文件 "file" 缺少依赖项 "依赖项"。 你的项目仍可能会生成，但可能会在找到此文件之前继续显示。

例如，文件 (资源文件或 .idl odl 文件包含项目系统无法解析的 include 语句。

因为项目系统不会处理预处理器语句 ( # if （如) ），所以有问题的语句实际上可能并不是生成的一部分。

若要解决此警告，请在 .rc 文件中删除所有不必要的代码，或添加相应名称的占位符文件。
