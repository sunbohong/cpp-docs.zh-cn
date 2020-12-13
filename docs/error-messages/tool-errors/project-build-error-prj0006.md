---
description: 了解详细信息：项目生成错误 PRJ0006
title: 项目生成错误 PRJ0006
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: a78646c843a6c6df3b4e2847076670492a9efb6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343920"
---
# <a name="project-build-error-prj0006"></a>项目生成错误 PRJ0006

无法打开临时文件 "file"。 请确保该文件存在，并且该目录不是写保护的。

Visual C++ 无法在生成过程中创建临时文件。 此问题的原因包括：

- 无临时目录。

- 只读临时目录。

- 磁盘空间不足。

- $ (IntDir) 文件夹为只读，或者包含只读的临时文件。

错误 PRJ0007：无法创建输出目录 "directory" 时，也会发生此错误。 错误 PRJ0007 表示无法创建 $ (IntDir) 目录，这意味着暂时创建文件也会失败。

每次指定时都会创建临时文件：

- 响应文件。

- 自定义生成步骤。

- 生成事件。
