---
description: 了解详细信息：假定
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: b597e50dafe07950d87cb04cf5e697b63c55611c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121740"
---
# <a name="assume"></a>ASSUME

启用寄存器值的错误检查。 仅 (32 位 MASM。 ) 

## <a name="syntax"></a>语法

> **假定**  *segregister*__：__*name* ⟦__，__ *segregister*__：__*name*.。。⟧\
> **假定**  *dataregister*__：__*type* ⟦__，__ *dataregister*__：__*type*.。。⟧\
> **假设**  *注册*__：错误__ ⟦__，__ *注册*__：错误__.。。⟧\
> **假设**  ⟦*register*__：__⟧**NOTHING** ⟦__，__ *register*__： nothing__⟧

## <a name="remarks"></a>备注

**假设** 生效后，汇编程序会监视给定寄存器值的更改。 如果使用了寄存器，则 **错误** 将生成错误。 不 **会删除注册** 错误检查。 可以在一个语句中组合不同种类的假设。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
