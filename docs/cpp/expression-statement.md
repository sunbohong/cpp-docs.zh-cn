---
description: 了解详细信息： Expression 语句
title: 表达式语句
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
ms.openlocfilehash: a208951c536883f2f08a6e856e9da48884255b1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186540"
---
# <a name="expression-statement"></a>表达式语句

表达式语句导致计算表达式。 出于表达式语句的原因，不会发生控制或迭代的传输。

表达式语句的语法就是

## <a name="syntax"></a>语法

```
[expression ] ;
```

## <a name="remarks"></a>备注

在执行下一个语句前，将计算表达式语句中的所有表达式并完成所有副作用。 最常用的表达式语句是赋值和函数调用。  由于表达式是可选的，因此分号单独被视为空的表达式语句，称为 [null](../cpp/null-statement.md) 语句。

## <a name="see-also"></a>请参阅

[C + + 语句概述](../cpp/overview-of-cpp-statements.md)
