---
description: 了解更多：编译器警告 C4962
title: 编译器警告 C4962
ms.date: 11/04/2016
f1_keywords:
- C4962
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
ms.openlocfilehash: a263f89c0b57eca07f0ab27758163052586eda03
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336064"
---
# <a name="compiler-warning-c4962"></a>编译器警告 C4962

“function”：已禁用按配置文件优化，原因在于优化导致了配置数据文件不一致

函数不是使用 /LTCG:PGO 编译的，因为该函数的计数（分析）数据不可靠。 重做分析以重新生成包含该函数不可靠分析数据的 .pgc 文件。

默认情况下，此警告处于关闭状态。 有关详细信息，请参阅 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。
