---
description: 了解详细信息：。PUSHREG
title: .PUSHREG
ms.date: 12/16/2019
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: b9316cebad76747c69cb577fcae71f28b6bd9530
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131256"
---
# <a name="pushreg"></a>.PUSHREG

`UWOP_PUSH_NONVOL`使用序言中的当前偏移量生成指定寄存器号的展开代码项。

## <a name="syntax"></a>语法

> .PUSHREG register

## <a name="remarks"></a>备注

**.PUSHREG** 允许 ml64.exe 用户指定框架函数的展开方式，并且仅在序言内允许，该函数从 [过程](proc.md)**框架** 声明扩展到 [。ENDPROLOG](dot-endprolog.md)指令。 这些指令不生成代码;它们仅生成 `.xdata` 和 `.pdata` 。 **.PUSHREG** 后面应是实际实现要展开的操作的说明。 最好将展开指令和它们要展开的代码封装在一个宏中，以确保协议。

*注册* 可以是以下项之一： \
RAX |RCX |RDX |RBX |RDI.TPL |RSI |RBP |R8 |R9 |R10 |R11 |R12 |R13 |R14 |R15.

有关详细信息，请参阅 [MASM ( # A0) ](masm-for-x64-ml64-exe.md)。

## <a name="sample"></a>示例

### <a name="description"></a>说明

下面的示例演示如何推送非易失性寄存器。

### <a name="code"></a>代码

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
