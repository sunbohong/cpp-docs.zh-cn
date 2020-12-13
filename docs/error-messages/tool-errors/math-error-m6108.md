---
description: 了解详细信息：数学错误 M6108
title: 数学错误 M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: 1a0acf13bd166e499334cb13de33093c2c804f5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143879"
---
# <a name="math-error-m6108"></a>数学错误 M6108

平方根

平方根运算中的操作数为负数。

程序终止，退出代码为136。

> [!NOTE]
> `sqrt`C 运行时库中的函数和 FORTRAN 内部函数 **SQRT** 不会生成此错误。 C `sqrt` 函数在执行操作之前检查参数，如果操作数为负，则返回一个错误值。 FORTRAN **SQRT** 函数生成域错误 [M6201](../../error-messages/tool-errors/math-error-m6201.md) ，而不是此错误。
