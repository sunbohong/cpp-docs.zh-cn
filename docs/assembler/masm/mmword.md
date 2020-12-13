---
description: 了解详细信息： MMWORD
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: f0e888efcfea7c1ca94129ff3e4cd2f40644ae13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128228"
---
# <a name="mmword"></a>MMWORD

用于具有 MMX 和 SSE 的64位多媒体操作数 (XMM) 说明。

## <a name="syntax"></a>语法

> **MMWORD**

## <a name="remarks"></a>备注

**MMWORD** 是一种类型。  在将 **MMWORD** 添加到 MASM 之前，可通过以下方式实现等效功能：

```asm
    mov mm0, qword ptr [ebx]
```

尽管两个指令都适用于64位操作数，但 **QWORD** 是64位无符号整数的类型， **MMWORD** 是64位多媒体值的类型。

**MMWORD** 用于表示与 [__m64](../../cpp/m64.md)相同的类型。

## <a name="example"></a>示例

```asm
    movq     mm0, mmword ptr [ebx]
```

## <a name="see-also"></a>另请参阅

[MASM BNF 语法](masm-bnf-grammar.md)
