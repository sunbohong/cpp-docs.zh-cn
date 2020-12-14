---
description: 详细了解：编译器警告 (级别 4) C4960
title: 编译器警告（等级 4）C4960
ms.date: 11/04/2016
f1_keywords:
- C4960
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
ms.openlocfilehash: 9a1e3d5390ffa4ffad101d1ea2c3164c04d12ca8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234574"
---
# <a name="compiler-warning-level-4-c4960"></a>编译器警告（等级 4）C4960

“function”太大，无法配置

当使用 [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)时，编译器检测到某个输入模块的函数具有的指令超过 65,535 条。 如此大的函数不可用于按配置进行的优化。

若要解决此警告，请减小该函数的大小。
