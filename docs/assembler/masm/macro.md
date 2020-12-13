---
description: 了解详细信息：宏
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 5410357e76d28cddd54f3c90a34d3e85b8629143
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129735"
---
# <a name="macro"></a>MACRO

标记名为 *name* 的宏块，并为调用宏时传递的参数建立 *参数* 占位符。

## <a name="syntax"></a>语法

> *name***宏**⟦*参数*⟦**：** 请求 |： =*默认*  |  *参数* **： VARARG**⟧ .。。⟧\  
> *前瞻性*\
⟦**GOTO** ：*macrolabelId*⟧ \
> ⟦**EXITM**⟧ \
> **ENDM** ⟦*value*⟧

## <a name="remarks"></a>备注

宏函数将 *值* 返回给调用语句。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[GOTO (MASM) ](goto-masm.md)\
[ENDM](endm.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
