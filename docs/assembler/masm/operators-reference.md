---
description: 了解有关以下内容的详细信息： MASM 运算符引用
title: MASM 运算符引用
ms.date: 07/15/2020
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: 66169e591ed5839dfa0f45c4fe6bcf9febe6fe02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97126251"
---
# <a name="masm-operators-reference"></a>MASM 运算符引用

## <a name="arithmetic"></a>算术

:::row:::
   :::column span="":::
      [`*` (乘) ](operator-multiply.md)\
      [`+` (添加) ](operator-add.md)\
      [`-` (减或取反) ](operator-subtract-2.md)
   :::column-end:::
   :::column span="":::
      [`.` (字段) ](operator-dot.md)\
      [`/` (相除) ](operator-subtract-1.md)
   :::column-end:::
   :::column span="":::
      [`[]` (索引) ](operator-brackets.md)\
      [`MOD` (余数) ](operator-mod.md)
   :::column-end:::
:::row-end:::

## <a name="control-flow"></a>控制流

:::row:::
   :::column span="":::
      [`!` (运行时逻辑 not) ](operator-logical-not-masm-run-time.md)\
      [`!=` (运行时不相等) ](operator-not-equal-masm.md)\
      [`||` (运行时逻辑或) ](operator-logical-or.md)\
      [`&&` (运行时逻辑与) ](operator-logical-and-masm-run-time.md)\
      [`<` (运行时小于) ](operator-less-than-masm-run-time.md)
   :::column-end:::
   :::column span="":::
      [`<=` (运行时小于或等于) ](operator-less-or-equal-masm-run-time.md)\
      [`==` (运行时等于) ](operator-equal-masm-run-time.md)\
      [`>` (运行时大于) ](operator-greater-than-masm-run-time.md)\
      [`>=` (运行时大于或等于) ](operator-greater-or-equal-masm-run-time.md)\
      [`&` (运行时位与) ](operator-bitwise-and.md)
   :::column-end:::
   :::column span="":::
      [`CARRY?` (运行时执行测试) ](operator-carry-q.md)\
      [`OVERFLOW?` (运行时溢出测试) ](operator-overflow-q.md)\
      [`PARITY?` (运行时奇偶校验测试) ](operator-parity-q.md)\
      [`SIGN?` (运行时签名测试) ](operator-sign-q.md)\
      [`ZERO?` (运行时零测试) ](operator-zero-q.md)
   :::column-end:::
:::row-end:::

## <a name="logical-and-shift"></a>逻辑与移位

:::row:::
   :::column span="":::
      [`AND` (位与) ](operator-and.md)\
      [`NOT` (按位 not) ](operator-not.md)
   :::column-end:::
   :::column span="":::
      [`OR` (位或) ](operator-or.md)\
      [`SHL` 左 (移位位数) ](operator-shl.md)
   :::column-end:::
   :::column span="":::
      [`SHR` 向右 (移位位数) ](operator-shr.md)\
      [`XOR` (按位异或) ](operator-xor.md)
   :::column-end:::
:::row-end:::

## <a name="macro"></a>宏

:::row:::
   :::column span="":::
      [`!` (字符文本) ](operator-logical-not-masm.md)\
      [`%` (视为文本) ](operator-percent.md)
   :::column-end:::
   :::column span="":::
      [`;;` (视为注释) ](operator-semicolons.md)\
      [`< >` (视为一个文本) ](operator-literal.md)
   :::column-end:::
   :::column span="":::
      [`& &` (替换参数值) ](operator-logical-and-masm.md)
   :::column-end:::
:::row-end:::

## <a name="miscellaneous"></a>杂项

:::row:::
   :::column span="":::
      [`' '` (视为 string) ](operator-single-quote.md)\
      [`" "` (视为 string) ](operator-double-quote.md)\
      `:` (本地标签定义) 
   :::column-end:::
   :::column span="":::
      `::` (注册段和偏移量) \
      `::` (全局标签定义) 
   :::column-end:::
   :::column span="":::
      [`;` (视为注释) ](operator-semicolon.md)\
      [`DUP` (重复声明) ](operator-dup.md)
   :::column-end:::
:::row-end:::

## <a name="record"></a>记录

:::row:::
   :::column span="":::
      [`MASK` (获取记录或字段位掩码) ](operator-mask.md)
   :::column-end:::
   :::column span="2":::
      [`WIDTH` (获取记录或字段宽度) ](operator-width.md)
   :::column-end:::
:::row-end:::

## <a name="relational"></a>关系

:::row:::
   :::column span="":::
      [`EQ` (等于) ](operator-eq.md)\
      [`GE` (大于或等于) ](operator-ge.md)
   :::column-end:::
   :::column span="":::
      [`GT` (大于) ](operator-gt.md)\
      [`LE` (小于或等于) ](operator-le.md)
   :::column-end:::
   :::column span="":::
      [`LT` (小于) ](operator-lt.md)\
      [`NE` (不等于) ](operator-ne.md)
   :::column-end:::
:::row-end:::

## <a name="segment"></a>段

:::row:::
   :::column span="":::
      [`:` (段重写) ](operator-colon.md)\
      `::` (注册段和偏移量) \
      [`IMAGEREL` (图像相对偏移) ](operator-imagerel.md)
   :::column-end:::
   :::column span="":::
      [`LROFFSET` (加载器解析的偏移量) ](operator-lroffset.md)\
      [`OFFSET` (段相对偏移) ](operator-offset.md)
   :::column-end:::
   :::column span="":::
      [`SECTIONREL` (节相对偏移) ](operator-sectionrel.md)\
      [`SEG` (获取段) ](operator-seg.md)
   :::column-end:::
:::row-end:::

## <a name="type"></a>类型

:::row:::
   :::column span="":::
      [`HIGH` (高8位，最低16位) ](operator-high.md)\
      [`HIGH32` 64位 (高32位) ](operator-high32.md)\
      [`HIGHWORD` (高16位的最低32位) ](operator-highword.md)\
      [`LENGTH` 数组中 (元素数) ](operator-length.md)\
      [`LENGTHOF` 数组中 (元素数) ](operator-lengthof.md)\
      [`LOW` (低8位) ](operator-low.md)
   :::column-end:::
   :::column span="":::
      [`LOW32` (低32位) ](operator-low32.md)\
      [`LOWWORD` (低16位) ](operator-lowword.md)\
      [`OPATTR` (获取参数类型信息) ](operator-opattr.md)\
      [`PTR` 指向或类型的 (指针) ](operator-ptr.md)\
      [`SHORT` 标记简短标签类型 () ](operator-short.md)
   :::column-end:::
   :::column span="":::
      [`SIZE` 类型或变量的 (大小) ](operator-size.md)\
      [`SIZEOF` 类型或变量的 (大小) ](operator-sizeof.md)\
      [`THIS` (当前位置) ](operator-this.md)\
      [`TYPE` (获取表达式类型) ](operator-type.md)\
      [`.TYPE` (获取参数类型信息) ](operator-dot-type.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>请参阅

[Microsoft 宏汇编程序参考](microsoft-macro-assembler-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
