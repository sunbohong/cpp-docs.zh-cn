---
description: 了解详细信息：严重错误 C1210
title: 错误 C1210
ms.date: 11/04/2016
f1_keywords:
- C1210
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
ms.openlocfilehash: 6437d5894b0f3b4156dedc53f1a121ba85e7516f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267945"
---
# <a name="fatal-error-c1210"></a>错误 C1210

> 安装的运行时版本不支持 /clr:pure 和 /clr:safe

**/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

使用的编译器是当前版本而公共语言运行时是早期版本时将发生 C1210。

编译器的一些功能在早期的运行时版本中可能无效。

若要解决 C1210，请安装适用于你的编译器的公共语言运行时版本。
