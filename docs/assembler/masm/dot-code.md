---
description: 了解详细信息：。编写
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 3f47b3bf9f345ae39f68b1b21e8f3807f554ea2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132270"
---
# <a name="code"></a>.CODE

仅 (32 位 MASM [。与一起使用时，) 。模型](dot-model.md)，指示代码段的开头。

## <a name="syntax"></a>语法

> **.CODE** ⟦*name*⟧ \
> ⟦ *segmentItem* ⟧ ... \
> ⟦ *codesegmentnameId* **结束**;⟧\

### <a name="parameters"></a>parameters

*路径名*\
可选参数，用于指定代码段的名称。 对于小型、小型、紧凑型和平面 [模型](dot-model.md)，默认名称是 **_TEXT** 。 对于其他模型，默认名称为 *modulename* _TEXT。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[.数据](dot-data.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
