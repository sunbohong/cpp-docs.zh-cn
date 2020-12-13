---
description: '了解详细信息：。.DOSSEG (32 位 MASM) '
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 636f3f811b20e7cf9955648c71025cfb1766fb47
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132101"
---
# <a name="dosseg-32-bit-masm"></a>..DOSSEG (32 位 MASM) 

根据 MS-DOS 段约定对段进行排序：代码优先，然后是不在 DGROUP 中的段，然后是 DGROUP 中的段。 仅 (32 位 MASM。 ) 

## <a name="syntax"></a>语法

> **..DOSSEG**

## <a name="remarks"></a>备注

DGROUP 中的段遵循以下顺序：段不在 BSS 或 STACK 中，然后是 BSS 段，最后是堆栈段。 主要用于确保 MASM 独立程序中的 CodeView 支持。 与 [.dosseg](dosseg.md)相同。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
