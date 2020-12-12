---
description: 了解详细信息：偶和 ALIGN 指令
title: EVEN 和 ALIGN 指令
ms.date: 08/30/2018
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
ms.openlocfilehash: adf633e99f1cb52a7849de24751d065a0344798f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117791"
---
# <a name="even-and-align-directives"></a>EVEN 和 ALIGN 指令

**Microsoft 专用**

尽管内联汇编程序不支持大多数 MASM 指令，但它确实支持 `EVEN` 和 **对齐**。 根据需要，这些指令将 **NOP** (不会在程序集代码中) 指令进行操作，以将标签与特定边界对齐。 对某些处理器来说，这使得指令取回操作更加有效。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[在 __asm 块中使用汇编语言](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
