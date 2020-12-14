---
description: 了解详细信息：严重错误 C1854
title: 错误 C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: 1c08db55089853545afa511213fc164c978bd4ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276200"
---
# <a name="fatal-error-c1854"></a>错误 C1854

> 无法覆盖在对象文件 "*filename*" 中创建预编译头过程中形成的信息

指定了/Yu (在为同一文件指定[/yc (创建预编译头文件) ](../../build/reference/yc-create-precompiled-header-file.md)选项后[使用预编译头文件) ](../../build/reference/yu-use-precompiled-header-file.md)选项。

若要解决此问题，一般情况下，只使用 **/yc** 选项设置项目中的一个文件，并使用 **/yu** 选项设置要编译的所有其他文件。 有关使用 **/yc** 选项的详细信息以及如何在 VISUAL Studio IDE 中设置该选项的详细信息，请参阅 [/Yc (创建预编译头文件)](../../build/reference/yc-create-precompiled-header-file.md)。 有关使用预编译标头的详细信息，请参阅 [创建预编译头文件](../../build/creating-precompiled-header-files.md)。
