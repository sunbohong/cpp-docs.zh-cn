---
description: 了解详细信息：本地
title: LOCAL (MASM)
ms.date: 12/16/2019
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 27296f69b62de0dcd314b2575f045e06576bbf64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129748"
---
# <a name="local"></a>LOCAL

在第一个指令中，在宏内， **本地** 定义宏的每个实例特有的标签。

## <a name="syntax"></a>语法

> **LOCAL** *LocalId* ⟦， *localId* .。。⟧
>
> **LOCAL** *面部*⟦ __\[__ *count*__]__ ⟧⟦__：__*qualifiedType*⟧⟦__，__ *面部*⟦ __\[__ *count*__]__ ⟧⟦*qualifiedType*⟧ .。。⟧

## <a name="remarks"></a>备注

在第二个指令中，在过程定义中 (**PROC**) ， **本地** 创建在过程中存在的基于堆栈的变量。 *面部* 可以是一个简单变量或包含 *count* 元素的数组，其中 *count* 是一个常量表达式。

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
