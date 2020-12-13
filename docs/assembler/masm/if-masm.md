---
description: 了解详细信息：
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 09b4bd09155ef848ad165b4e8b0d3a093ade0008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130204"
---
# <a name="if"></a>IF

如果表达式1为)  (true，则为 *ifstatements* 的程序 *集，如果**表达式* 1 为 false (0) 并且 *表达式* 2 为 true，则为 *elseifstatements* 。

## <a name="syntax"></a>语法

> **IF** *表达式*\
> *if 语句*\
> ⟦**ELSEIF** *表达式* 2\
> *elseif-语句*⟧ \
> ⟦**ELSE**\
> *else-语句*⟧ \
> **ENDIF**

## <a name="remarks"></a>备注

以下指令可以替换为 [ELSEIF](elseif-masm.md)： **ELSEIFB**、 **ELSEIFDEF**、 **ELSEIFDIF**、 **ELSEIFDIFI**、 **ELSEIFE**、 **ELSEIFIDN**、 **ELSEIFIDNI**、 **ELSEIFNB** 和 **ELSEIFNDEF**。 （可选）如果上一个表达式为 false，则汇编 *else 语句* 。 请注意，将在程序集时间对表达式进行计算。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
