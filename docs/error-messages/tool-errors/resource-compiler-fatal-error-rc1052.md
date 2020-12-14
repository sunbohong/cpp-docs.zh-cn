---
description: 了解更多：资源编译器错误 RC1052
title: 资源编译器错误 RC1052
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: 41ef30cfde7d463337b1747b3f6141866e39e3be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255075"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>资源编译器错误 RC1052

编译器限制： #if 或 #ifdef 块嵌套太深

程序已超出 `#if` 和 `#ifdef` 指令的最大允许嵌套级别。

此错误可能由使用这些预处理器指令的包含文件造成。

若要解决此问题，请减少资源文件中嵌套的 `#if` 和 `#ifdef` 指令的数量。 如果此问题是由资源文件中所包含的头文件造成的，请减少头文件中嵌套的 `#if` 和 `#ifdef` 指令。 如果无法做到这一点，请考虑通过在现有的已包含头文件上运行预处理器，以在资源文件中创建和包含一个新的头文件。 有关详细信息，请参阅 [/p (预处理到文件) ](../../build/reference/p-preprocess-to-a-file.md) 编译器选项。
