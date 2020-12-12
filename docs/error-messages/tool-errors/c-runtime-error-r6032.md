---
description: 了解更多： C 运行时错误 R6032
title: C 运行时错误 R6032
ms.date: 11/04/2016
f1_keywords:
- R6032
helpviewer_keywords:
- R6032
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
ms.openlocfilehash: b0fbc7730867fb6e9045adf4e5e2b8667f741784
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275888"
---
# <a name="c-runtime-error-r6032"></a>C 运行时错误 R6032

没有足够的空间用于区域设置信息

> [!NOTE]
> 如果在运行应用程序时遇到此错误消息，则该应用程序已关闭，因为它具有内部内存问题。 此错误有几个可能的原因，但通常是由于内存不足或程序中的 bug 引起的。
>
> 可以尝试以下步骤来修复此错误：
>
> - 关闭其他正在运行的应用程序或重新启动计算机以释放内存。
> - 使用 **控制面板** 中的 "**应用和功能**" 或 "**程序和功能**" 页来修复或重新安装该程序。
> - 检查 "**控制面板**" 中的 "软件更新" **Windows 更新**。
> - 检查应用的更新版本。 如果问题仍然存在，请与应用程序供应商联系。

**面向程序员的信息**

运行时在每个线程上维护有关区域设置的信息，以便能够处理对与区域设置相关的函数的调用。 如果此信息的内存分配失败，则运行时无法继续，因为它的许多基本设施依赖于它。
