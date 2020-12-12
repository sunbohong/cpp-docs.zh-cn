---
description: 详细了解：编译器警告 (级别 4) C4611
title: 编译器警告（等级 4）C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: df53392b2d56b9afb1ab0cbcb2fc7b6267d5f00f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168262"
---
# <a name="compiler-warning-level-4-c4611"></a>编译器警告（等级 4）C4611

"function" 和 c + + 对象析构之间的交互是不可移植的

在某些平台上，包含的函数在 **`catch`** 超出范围时可能不支持析构函数的 c + + 对象语义。

若要避免意外的行为，请避免 **`catch`** 在具有构造函数和析构函数的函数中使用。

此警告只发出一次;请参阅 [杂注警告](../../preprocessor/warning.md)。
