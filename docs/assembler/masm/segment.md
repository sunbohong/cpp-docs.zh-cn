---
description: 了解详细信息：段
title: SEGMENT
ms.date: 12/16/2019
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: aeb99080043cbfb13fdec1c2e82df3a6d16b306d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97125588"
---
# <a name="segment"></a>SEGMENT

定义名为 *name* 且带有段特性的程序段

## <a name="syntax"></a>语法

> *name* **SEGMENT** ⟦**READONLY**⟧⟦*align*⟧⟦*合并*⟧⟦*use*⟧⟦*特征*⟧ **ALIAS (** _string_ **)** ⟦__"__*class*__"__⟧ \
> *前瞻性*\
> *名称***结束**

#### <a name="parameters"></a>parameters

*垂直*\
可以从中选择段的起始地址的内存地址范围。 对齐类型可以是以下任一项：

|对齐类型|起始地址|
|----------------|----------------------|
|**BYTE**|下一个可用的字节地址。|
|**WORD**|下一个可用的单词地址 (每个单词) 2 个字节。|
|**DWORD**|下一个可用的双字地址 (每个双引号) 4 个字节。|
|**分页**|下一个可用的段落地址)  (每个段落16个字节。|
|**分页**|下一个可用的页地址 (每页256字节) 。|
|**对齐** (*n*) |下一个可用的第 *n* 个字节地址。 有关详细信息，请参阅备注部分。|

如果未指定此参数，则默认情况下使用 **段落** 。

仅将 (32 位 MASM *合并*) \
**PUBLIC**、 **STACK**、 **COMMON**、 **MEMORY**、 **AT**<em>address</em>、 **PRIVATE**

仅 *使用* (32 位 MASM) \
**USE16**， **USE32**， **平面**

*共性*\
**INFO**、 **READ**、 **WRITE**、 **EXECUTE**、 **SHARED**、 **NOPAGE**、 **NOCACHE** 和 **放弃**

这些支持仅适用于 COFF，并对应于类似名称的 COFF 部分特征 (例如， **SHARED** 对应于 IMAGE_SCN_MEM_SHARED) 。 READ 设置 IMAGE_SCN_MEM_READ 标志。 过时的 READONLY 标志导致部分清除 IMG_SCN_MEM_WRITE 标志。 如果设置了任何 *特征* ，则不会使用默认特征，并且只有程序员指定的标志才有效。

_类似_\
此字符串用作发出的 COFF 对象中的节名。  用不同的 MASM 段名称创建多个具有相同外部名称的节。

不支持 **/omf**。

*班级*\
指定应如何在已组合的文件中组合和排序段。 典型值为、 `'DATA'` 、 `'CODE'` `'CONST'` 和 `'STACK'`

## <a name="remarks"></a>备注

对于 `ALIGN(n)` ， *n* 可以是从1到8192的任何2的幂; 不支持 **/omf**。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
