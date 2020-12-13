---
description: 了解详细信息：。SAVEXMM128
title: .SAVEXMM128
ms.date: 12/17/2019
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 697598aa5820b029d19da62a817c60455059865e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131113"
---
# <a name="savexmm128"></a>.SAVEXMM128

`UWOP_SAVE_XMM128` `UWOP_SAVE_XMM128_FAR` 使用当前的序言偏移量生成指定 XMM 寄存器的或展开代码项。 MASM 将选择最有效的编码。

## <a name="syntax"></a>语法

> **.SAVEXMM128** *xmmreg* ， *偏移量*

## <a name="remarks"></a>备注

**.SAVEXMM128** 允许 ml64.exe 用户指定框架函数的展开方式，并且仅在序言内允许，该函数从 [过程](proc.md) 框架声明扩展到 [。ENDPROLOG](dot-endprolog.md) 指令。 这些指令不生成代码;它们仅生成 `.xdata` 和 `.pdata` 。 .SAVEXMM128 后面应是实际实现要展开的操作的说明。 最好将展开指令和它们要展开的代码封装在一个宏中，以确保协议。

*偏移量* 必须是16的倍数。

有关详细信息，请参阅 [MASM ( # A0) ](masm-for-x64-ml64-exe.md)。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
