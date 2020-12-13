---
description: 了解详细信息：。ALLOCSTACK
title: .ALLOCSTACK
ms.date: 12/17/2019
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: 6075b0900df104ae5faeaaff1dc0de2d3727b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132361"
---
# <a name="allocstack"></a>.ALLOCSTACK

为序言中的当前偏移量生成指定大小的 **UWOP_ALLOC_SMALL** 或 **UWOP_ALLOC_LARGE** 。

## <a name="syntax"></a>语法

> **.ALLOCSTACK** *大小*

## <a name="remarks"></a>备注

MASM 将为给定大小选择最有效的编码。

**.ALLOCSTACK** 允许 ml64.exe 用户指定框架函数的展开方式，并且仅允许在序言内进行扩展，这种情况下，它从 [过程](proc.md) 框架声明扩展到 [。ENDPROLOG](dot-endprolog.md) 指令。 这些指令不生成代码;它们仅生成 `.xdata` 和 `.pdata` 。 **.ALLOCSTACK** 后面应是实际实现要展开的操作的说明。 最好将展开指令和它们要展开的代码封装在一个宏中，以确保协议。

size  操作数必须是 8 的倍数。

有关详细信息，请参阅 [MASM ( # A0) ](masm-for-x64-ml64-exe.md)。

## <a name="sample"></a>示例

下面的示例演示如何指定展开/异常处理程序：

```asm
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console
text SEGMENT
PUBLIC Example3
PUBLIC Example3_UW
Example3_UW PROC NEAR
   ; exception/unwind handler body

   ret 0

Example3_UW ENDP

Example3 PROC FRAME : Example3_UW

   sub rsp, 16
.allocstack 16

.endprolog

   ; function body
    add rsp, 16
   ret 0

Example3 ENDP
text ENDS
END
```

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
