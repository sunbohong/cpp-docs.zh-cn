---
description: 了解详细信息：调用
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: eb372ad3d7ccde9f217f55ed9817acfe9bd8f1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129839"
---
# <a name="invoke"></a>INVOKE

仅 (32 位 MASM。 ) 调用由 *expression* 给定的地址处的过程，并根据语言类型的标准调用约定传递堆栈上或寄存器中的参数。

## <a name="syntax"></a>语法

> **调用** *expression* ⟦__，__ *argument* .。。⟧

## <a name="remarks"></a>备注

传递给过程的每个参数可以是表达式、寄存器对或地址表达式 (**前面是 address) 的** 表达式。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
