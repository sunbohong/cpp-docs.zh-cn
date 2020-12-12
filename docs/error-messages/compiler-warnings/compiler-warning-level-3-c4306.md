---
description: 详细了解：编译器警告 (等级 3) C4306
title: 编译器警告（等级 3）C4306
ms.date: 08/27/2018
f1_keywords:
- C4306
helpviewer_keywords:
- C4306
ms.assetid: 5b2192d7-402d-4b6d-8619-08105e7dcac7
ms.openlocfilehash: 1140371bdc9f330c058ee336f5f8723d1834a93b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344050"
---
# <a name="compiler-warning-level-3-c4306"></a>编译器警告（等级 3）C4306

> "*identifier*"：从 "*type1*" 转换为 "*type2*" 的大小更大

标识符的类型强制转换为更大的指针。 新类型的未填充的高位将填充零。

此警告可能表示存在不需要的转换。 生成的指针可能无效。
