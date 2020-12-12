---
description: 了解详细信息： ARM 汇编程序诊断消息
title: ARM 汇编程序诊断消息
ms.date: 08/30/2018
f1_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
helpviewer_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
ms.openlocfilehash: 91e4640c161cbb58522c3680ae5decdb4cc1e992
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118194"
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM 汇编程序诊断消息

Microsoft ARM 组装器 (*armasm*) 在遇到诊断警告和错误时发出这些警告和错误。 本文介绍最常遇到的消息。

## <a name="syntax"></a>语法

> <em>filename</em> **(**<em>行号</em>**) ：** \[ **错误** | **警告**] <em>数字</em>**：** *消息*

## <a name="diagnostic-messages---errors"></a>诊断消息-错误

> A2193：此指令生成不可预知的行为

ARM 体系结构无法保证执行此指令时将发生的情况。  有关此说明的明确定义形式的详细信息，请参阅 [ARM 体系结构参考手册](https://go.microsoft.com/fwlink/p/?linkid=246464)。

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196：无法以16位编码指令

无法将指定的指令编码为16位拇指指令。  指定32位指令，或重新排列代码，使目标标签成为16位指令的范围。

汇编程序可能会尝试对16位的分支进行编码，并会由于此错误而失败，即使 encodable 了32位分支也是如此。 可以通过使用 `.W` 说明符将分支显式标记为32位来解决此问题。

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202：块区中不允许使用 UAL 指令语法

Thumb 代码必须使用统一汇编程序语言 (UAL) 语法。  不再接受旧语法

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513：旋转甚至必须为

在 ARM 模式下，有一个用于指定常量的替代语法。  您可以编写，而不是编写，而是 `#<const>` `#<byte>,#<rot>` 表示通过向右旋转值而获得的常量值 `<byte>` `<rot>` 。  使用此语法时，必须将值设置为 `<rot>` 偶数。

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557：要写回的字节数不正确

在霓虹灯结构加载和存储说明 (`VLDn` 中， `VSTn`) ，可以使用另一种语法来指定对基寄存器的写回。  您可以指定一个即时值来指示要添加到基寄存器的偏移量，而不是在地址后 (！ ) 。  如果使用此语法，则必须指定指令加载或存储的确切字节数。

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>诊断消息-警告

> A4228：对齐值超出了区域对齐方式;不保证对齐

指令中指定的对齐方式 `ALIGN` 大于封闭的对齐方式 `AREA` 。  因此，汇编程序无法保证 `ALIGN` 将遵循指令。

若要解决此问题，可以在指令上指定 `AREA` 一个大于 `ALIGN` 或等于所需对齐方式的特性。

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508：不推荐使用此旋转常量

在 ARM 模式下，有一个用于指定常量的替代语法。  您可以编写，而不是编写，而是 `#<const>` `#<byte>,#<rot>` 表示通过向右旋转值而获得的常量值 `<byte>` `<rot>` 。  在某些上下文中，ARM 弃用了这些旋转常量的使用。 在这些情况下，请改用基本 `#<const>` 语法。

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509：不推荐使用这种形式的条件指令

此形式的条件指令已在 ARMv8 体系结构中由 ARM 弃用。 建议更改代码以使用条件分支。 若要查看仍支持的条件指令，请参阅 [ARM 体系结构参考手册](https://go.microsoft.com/fwlink/p/?linkid=246464)。

使用 **-oldit** 命令行开关时，不会发出此警告。

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>请参阅

[ARM 汇编程序 Command-Line 参考](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM 汇编程序指令](../../assembler/arm/arm-assembler-directives.md)<br/>
