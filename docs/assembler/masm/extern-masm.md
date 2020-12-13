---
description: 了解详细信息： EXTERN
title: EXTERN (MASM)
ms.date: 12/06/2019
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 354a390a16fb663dc6e907e37022a362c3ab5648
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130346"
---
# <a name="extern"></a>EXTERN

定义一个或多个名为 *type**类型的外部* 变量、标签或符号。

## <a name="syntax"></a>语法

> **EXTERN** ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __：__ *type* ⟦__，__ ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __：__ *type* .。。⟧

## <a name="remarks"></a>备注

*语言类型* 参数仅在32位 MASM 中有效。

该 *类型* 可以是 [ABS](operator-abs.md)，后者将 *名称* 导入为常量。 与 [EXTRN](extrn.md)相同。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
