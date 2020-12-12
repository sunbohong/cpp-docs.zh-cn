---
description: 了解详细信息： ARM 汇编程序指令
title: ARM 汇编程序指令
ms.date: 08/30/2018
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
ms.openlocfilehash: 8362453f2113922c5e834d1d68583b4199cf8d4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118113"
---
# <a name="arm-assembler-directives"></a>ARM 汇编程序指令

大多数情况下，Microsoft ARM 组装器使用 arm 程序集语言，如 [Arm 编译器 Armasm 参考指南](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)中所述。 但是，某些程序集指令的 Microsoft 实现不同于 ARM 程序集指令。 本文介绍了不同之处。

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>ARM 程序集指令的 Microsoft 实现

- 图

   Microsoft ARM 组装器支持以下 `AREA` 属性： `ALIGN` 、 `CODE` 、 `CODEALIGN` 、 `DATA` 、 `NOINIT` 、 `READONLY` `READWRITE` `THUMB` `ARM` 、、和。

   除了 `THUMB` `ARM` [ARM 编译器 armasm 参考指南](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)中所述，所有操作都如所述。

   在 Microsoft ARM 汇编程序中， `THUMB` 指示 `CODE` 部分包含拇指代码，是部分的默认值 `CODE` 。  `ARM` 指示部分包含 ARM 代码。

- ATTR

   不支持。

- 16

   不受支持，因为它表示 Microsoft ARM 组装器不允许的预 UAL Thumb 语法。  `THUMB`改为使用指令，并使用 UAL 语法。

- 常见问题解答

   不支持通用区域的对齐规范。

- DCDO

   不支持。

- `DN`, `QN`, `SN`

   不支持在寄存器别名上指定类型或通道。

- ENTRY

   不支持。

- EQU

   不支持定义符号的类型规范。

- `EXPORT` 和 `GLOBAL`

   使用以下语法指定导出：

   > **导出** |**GLOBAL** <em>符号</em>{**[**<em>type</em>**]**}

   *符号* 是要导出的符号。  [*type*] （如指定）可以是 `[DATA]` 指示符号指向数据，还是 `[FUNC]` 指示符号指向代码。 `GLOBAL` 是 `EXPORT`的同义词。

- EXPORTAS

   不支持。

- 期限

   不支持。

- `FUNCTION` 和 `PROC`

   尽管程序集语法通过列出调用方保存的寄存器和被调用方保存的寄存器来支持对过程的自定义调用约定的规范，但 Microsoft ARM 汇编程序会接受语法，但会忽略寄存器列表。  汇编程序生成的调试信息仅支持默认调用约定。

- `IMPORT` 和 `EXTERN`

   使用以下语法指定导入：

   > **导入** |**EXTERN** *符号*{**，弱***别名*{**，类型** *t*}}

   *符号* 是要导入的符号的名称。

   如果 `WEAK` 指定了 *alias* ，则表明 *符号* 是一个弱的外部。 如果在链接时找不到它的定义，则对它的所有引用都将绑定到 *别名*。

   如果 `TYPE` 指定了 *t* ，则 *t* 指示链接器应如何尝试解析 *符号*。  以下 *t* 的值可能：

   |值|描述|
   |-|-|
   |1|不要对 *符号* 执行库搜索|
   |2|执行 *符号* 的库搜索|
   |3|*符号* 是 *别名* (默认值的别名) |

   `EXTERN` 是的同义词 `IMPORT` ，但只有在当前程序集中存在对 *符号* 的引用时，才会导入它。

- MACRO

   不支持使用变量来保存宏的条件代码。 宏参数的默认值不受支持。

- NOFP

   不支持。

- `OPT`, `TTL`, `SUBT`

   不受支持，因为 Microsoft ARM 组装器不生成列表。

- PRESERVE8

   不支持。

- .RELOC

   `RELOC n` 只能跟在指令或数据定义指令之后。 没有可重定位的 "匿名符号"。

- 需要

   不支持。

- REQUIRE8

   不支持。

- THUMBX

   不受支持，因为 Microsoft ARM 组装器不支持2EE 指令集。

## <a name="see-also"></a>请参阅

[ARM 汇编程序 Command-Line 参考](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM 汇编程序诊断消息](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
