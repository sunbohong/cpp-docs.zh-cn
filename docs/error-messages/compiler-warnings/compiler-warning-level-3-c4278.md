---
description: 详细了解：编译器警告 (等级 3) C4278
title: 编译器警告（等级 3）C4278
ms.date: 08/27/2018
f1_keywords:
- C4278
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
ms.openlocfilehash: f7a53b54422e28f94096b91502651cb9355a244e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344141"
---
# <a name="compiler-warning-level-3-c4278"></a>编译器警告（等级 3）C4278

> "*identifier*"：类型库 "*tlb*" 中的标识符已经是宏;使用 "重命名" 限定符

使用 [#import](../../preprocessor/hash-import-directive-cpp.md)时，要导入的类型库中的标识符试图声明标识符 *标识符*。 但是，这已是一个有效符号。

使用 `#import` **rename** 特性为类型库中的符号分配别名。
