---
description: 了解详细信息：项目生成错误 PRJ0009
title: 项目生成错误 PRJ0009
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: 28a7a9ce1a4fa5f1b5b95ba208739b7172f0ac6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343881"
---
# <a name="project-build-error-prj0009"></a>项目生成错误 PRJ0009

未能打开生成日志以进行写入。

**请确保该文件未被其他进程打开并且未被写保护。**

在将 **生成日志记录** 属性设置为 **"是"** 并执行生成或重新生成后，Visual C++ 无法以独占模式打开生成日志。

通过打开 "**工具**" 菜单上的 "**选项**" 对话框 (检查 **生成日志记录** 设置，单击 "**选项**" "命令) ，然后选择"**项目**"文件夹中的" **VC + + 生成**"。 生成文件 BuildLog.htm 调用，并写入中间目录 $ (IntDir) 。

此错误的可能原因：

- 你正在运行 Visual C++ 的两个进程，并尝试同时在这两个过程中生成相同项目的相同配置。

- 在锁定文件的进程中打开生成日志文件。

- 用户没有创建文件的权限。

- 当前用户没有 BuildLog.htm 的文件的写访问权限。
