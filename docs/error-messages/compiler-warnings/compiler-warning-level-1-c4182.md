---
description: 了解详细信息：编译器警告 (等级 1) C4182
title: 编译器警告（等级 1）C4182
ms.date: 11/04/2016
f1_keywords:
- C4182
helpviewer_keywords:
- C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
ms.openlocfilehash: 975d3ceea5e2b7504fda5c7d33e88b52cda9e572
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266697"
---
# <a name="compiler-warning-level-1-c4182"></a>编译器警告（等级 1）C4182

\#include 嵌套级别为 "number" deep;可能的无限递归

由于嵌套的包含文件数量过多，编译器用尽了堆上的空间。 当包含文件包含在另一个包含文件中时，它就是嵌套的。

此消息是信息性消息，出现在错误 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)之前。
