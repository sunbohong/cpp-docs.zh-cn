---
description: 了解更多：资源编译器错误 RC1020
title: 资源编译器错误 RC1020
ms.date: 11/04/2016
f1_keywords:
- RC1020
helpviewer_keywords:
- RC1020
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
ms.openlocfilehash: a3ee2bd319cce9663c27030b523dd9e389158e45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341082"
---
# <a name="resource-compiler-fatal-error-rc1020"></a>资源编译器错误 RC1020

意外的 "#endif"

`#endif`出现指令，但没有匹配的 `#if` 、 **#ifdef** 或 **#ifndef** 指令。

请确保 `#endif` 每个 `#if` 、 **#ifdef** 和 **#ifndef** 语句都有匹配项。
