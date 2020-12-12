---
description: 了解详细信息： ALIAS
title: ALIAS (MASM)
ms.date: 12/17/2019
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 7d5072cec8ef56f3dd2202617b3274c958a25d66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121753"
---
# <a name="alias"></a>ALIAS

**ALIAS** 指令创建函数的替代名称。  这使你可以为函数创建多个名称，或创建允许链接器 ( # A0) 将旧函数映射到新函数的库。

## <a name="syntax"></a>语法

> **A \<**_alias_**> = \<**_actual-name_**>**

#### <a name="parameters"></a>parameters

*实际名称*\
函数或过程的实际名称。  尖括号是必需的。

*a*\
备用或别名。  尖括号是必需的。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
