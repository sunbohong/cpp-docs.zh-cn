---
description: 了解详细信息：严重错误 C1077
title: 错误 C1077
ms.date: 11/04/2016
f1_keywords:
- C1077
helpviewer_keywords:
- C1077
ms.assetid: 514d66f4-b512-479a-b793-ebf45c91e15b
ms.openlocfilehash: f659f4bf971c476cdc2559d41b0b8bd1a1d05311
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339315"
---
# <a name="fatal-error-c1077"></a>错误 C1077

编译器限制：命令行选项数不得超过其限定值

命令行选项数超过了内部限制。

可能多用 [/D](../../build/reference/d-preprocessor-definitions.md)定义的符号太多。 （改为将定义放置在头文件中。）
