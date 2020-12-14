---
description: 了解详细信息：编译器警告 (等级 1) C4276
title: 编译器警告（等级 1）C4276
ms.date: 11/04/2016
f1_keywords:
- C4276
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
ms.openlocfilehash: 14b13b2eb1e13d28f2b208e52ef71e1c729fe5e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311781"
---
# <a name="compiler-warning-level-1-c4276"></a>编译器警告（等级 1）C4276

"function"：未提供原型;假定没有参数

采用 [__stdcall](../../cpp/stdcall.md) 调用约定的函数的地址时，必须提供原型，以便编译器可以创建函数的修饰名。 由于 *函数* 不具有原型，因此，当创建修饰名称时，编译器将假定函数没有参数。
