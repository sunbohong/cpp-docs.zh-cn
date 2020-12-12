---
description: 了解更多： C 运行时错误 R6031
title: C 运行时错误 R6031
ms.date: 11/04/2016
f1_keywords:
- R6031
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
ms.openlocfilehash: cd3a9e62e4209df5aa232ac9df6b69ce8a63d10a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206612"
---
# <a name="c-runtime-error-r6031"></a>C 运行时错误 R6031

多次尝试初始化 CRT。 这表示应用程序中有 bug。

> [!NOTE]
> 如果在运行应用程序时遇到此错误消息，则该应用程序已关闭，因为它有一个内部问题。 这可能导致应用程序中出现 bug，或者应用程序使用的外接程序或扩展中的 bug。
>
> 可以尝试以下步骤来修复此错误：
>
> - 使用 **控制面板** 中的 "**应用和功能**" 或 "**程序和功能**" 页来修复或重新安装该程序。
> - 使用 **控制面板** 中的 "**应用和功能**" 或 "**程序和功能**" 页，可以删除、修复或重新安装应用程序使用的任何外接程序或扩展程序。
> - 检查 "**控制面板**" 中的 "软件更新" **Windows 更新**。
> - 检查应用的更新版本。 如果问题仍然存在，请与应用程序供应商联系。

**面向程序员的信息**

此诊断指示在加载程序锁定过程中正在执行 MSIL 指令。 有关详细信息，请参阅 [混合程序集的初始化](../../dotnet/initialization-of-mixed-assemblies.md)。
