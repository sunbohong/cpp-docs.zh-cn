---
description: 了解详细信息：项目生成错误 PRJ0008
title: 项目生成错误 PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 2ae4952dfd3e5c5f53a3f549536598402ce1fd48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343907"
---
# <a name="project-build-error-prj0008"></a>项目生成错误 PRJ0008

无法删除文件 "file"。

**请确保该文件未被其他进程打开并且未被写保护。**

在重新生成或清理过程中，Visual C++ 将删除生成的所有已知中间文件和输出文件，以及在 "[常规配置设置" 属性页](../../build/reference/general-property-page-project.md)中的 "**清理时要删除的扩展**" 属性中满足通配符规范的任何文件。

如果 Visual C++ 无法删除文件，则会看到此错误。 若要解决此错误，请为执行生成的用户将文件及其目录设置为可写。
