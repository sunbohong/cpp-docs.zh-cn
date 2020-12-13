---
description: 了解详细信息：。SAVEREG
title: .SAVEREG
ms.date: 12/16/2019
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 8b946c9b25c3f4dc6a4696b418e85487e20014eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131178"
---
# <a name="savereg"></a>.SAVEREG

`UWOP_SAVE_NONVOL` `UWOP_SAVE_NONVOL_FAR` 为指定的寄存器 (*reg*) 生成或展开代码项，并使用当前的序言偏移量) 偏移 (*偏移* 量。 MASM 将选择最有效的编码。

## <a name="syntax"></a>语法

> **.SAVEREG** *reg*__，__ *offset*

## <a name="remarks"></a>备注

**.SAVEREG** 允许 ml64.exe 用户指定框架函数的展开方式，并且仅允许在序言内进行扩展，这种情况下，它从 [过程](proc.md) 框架声明扩展到 [。ENDPROLOG](dot-endprolog.md) 指令。 这些指令不生成代码;它们仅生成 `.xdata` 和 `.pdata` 。 **.SAVEREG** 后面应是实际实现要展开的操作的说明。 最好将展开指令和它们要展开的代码封装在一个宏中，以确保协议。

有关详细信息，请参阅 [MASM ( # A0) ](masm-for-x64-ml64-exe.md)。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
