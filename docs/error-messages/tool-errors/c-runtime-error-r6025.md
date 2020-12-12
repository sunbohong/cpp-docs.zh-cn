---
description: 了解更多： C 运行时错误 R6025
title: C 运行时错误 R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 7bf3213d81e144f14f6eeb25f108f497267ec4d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237564"
---
# <a name="c-runtime-error-r6025"></a>C 运行时错误 R6025

纯虚函数调用

> [!NOTE]
> 如果在运行应用程序时遇到此错误消息，则该应用程序已关闭，因为它有一个内部问题。 此错误的最常见原因是应用中的 bug 或安装已损坏。
>
> 可以尝试以下步骤来修复此错误：
>
> - 使用 **控制面板** 中的 "**应用和功能**" 或 "**程序和功能**" 页来修复或重新安装该程序。
> - 检查 "**控制面板**" 中的 "软件更新" **Windows 更新**。
> - 检查应用的更新版本。 如果问题仍然存在，请与应用程序供应商联系。

**面向程序员的信息**

尚未实例化对象来处理纯虚函数调用。

此错误是由通过转换为派生类的类型创建的指针调用抽象基类中的虚函数引起的，但实际上是指向基类的指针。 当在 **`void`** <strong>\*</strong> **`void`** <strong>\*</strong> 基类的构造过程中创建时，当从转换为指向类的指针时，会发生这种情况。
