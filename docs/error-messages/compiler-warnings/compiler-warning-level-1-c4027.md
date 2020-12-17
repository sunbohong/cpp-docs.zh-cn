---
description: 详细了解编译器警告 (等级 1) C4027
title: 编译器警告（等级 1）C4027
ms.date: 12/16/2020
f1_keywords:
- C4027
helpviewer_keywords:
- C4027
ms.openlocfilehash: 1489ca32211854bcf1ef55d1a4ac806ab1611f43
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645171"
---
# <a name="compiler-warning-level-1-c4027"></a>编译器警告（等级 1）C4027

> 未用形参表声明的函数

函数声明没有形参，但在函数定义中有形参或在调用中有实参。

编译器在不带参数列表的函数名称的旧 C 样式前向声明上接受但发出警告。 以后调用此函数时，编译器将假定函数采用函数定义或调用中找到的类型的实参。 建议修改函数声明，使其与函数定义的签名相匹配。
