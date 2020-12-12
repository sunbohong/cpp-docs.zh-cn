---
description: 了解详细信息： XMMWORD
title: XMMWORD
ms.date: 12/17/2019
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 304ac53a29fa7912107d6d4e87ee6efd3924ac3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124977"
---
# <a name="xmmword"></a>XMMWORD

用于具有 MMX 和 SSE 的128位多媒体操作数 (XMM) 说明。

## <a name="syntax"></a>语法

> **XMMWORD**

## <a name="remarks"></a>备注

**XMMWORD** 用于表示与 [__m128](../../cpp/m128.md)相同的类型。

## <a name="example"></a>示例

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```

## <a name="see-also"></a>另请参阅

[MASM BNF 语法](masm-bnf-grammar.md)
