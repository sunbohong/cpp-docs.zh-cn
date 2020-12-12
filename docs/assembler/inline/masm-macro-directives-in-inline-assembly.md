---
description: 详细了解：内联程序集中的 MASM 宏指令
title: 内联程序集中的 MASM 宏指令
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 131066ad117e0f314ba0900e8ecd19eb4843c25b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117557"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>内联程序集中的 MASM 宏指令

**Microsoft 专用**

内联汇编程序不是宏汇编程序。 不能使用 MASM 宏指令 (**宏**、 `REPT` 、 **IRC**、 `IRP` 和 `ENDM`) 或宏运算符 (**<>** 、 **！**、 **&** 、 `%` 和 `.TYPE`) 。 **`__asm`** 但块可以使用 C 预处理器指令。 有关详细信息，请参阅 [在 __Asm 块中使用 C 或 c + +](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) 。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[在 __asm 块中使用汇编语言](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
