---
description: 了解更多：编译器错误 C2856
title: 编译器错误 C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 8594bc5902e13967084aa3695131d616a4cf04da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337555"
---
# <a name="compiler-error-c2856"></a>编译器错误 C2856

\#pragma hdrstop 不能在 #if 块内

`hdrstop`不能将杂注放置在条件编译块的正文内。

将 `#pragma hdrstop` 语句移动到块中未包含的区域 `#if/#endif` 。
