---
description: '了解详细信息：。如果 (32 位 MASM) '
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e6ce9695f90a90665aee1cdaf15167963360fe04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131672"
---
# <a name="if-32-bit-masm"></a>.如果 (32 位 MASM) 

生成测试 *condition1* (（例如，AX > 7) ）的代码，如果该条件为 true，则执行 *语句* 。 仅 (32 位 MASM。 ) 

## <a name="syntax"></a>语法

> **.如果** *condition1*\
> *前瞻性*\
> ⟦**。ELSEIF** *condition2*\
> *语句*⟧ \
> ⟦**。ELSE**\
> *语句*⟧ \
> **.ENDIF**

## <a name="remarks"></a>备注

如果为 [。否则](dot-else.md) ，如果原始条件为 false，则执行其语句。 请注意，将在运行时评估条件。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
