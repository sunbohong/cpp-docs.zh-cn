---
description: 了解详细信息： auto_inline 杂注
title: auto_inline 杂注
ms.date: 08/29/2019
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: f629bbe5dc47ba15bba5b2b55541509f421fcd8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301043"
---
# <a name="auto_inline-pragma"></a>auto_inline 杂注

排除在指定了 **off** 的范围内的任何函数被视为自动内联扩展的候选项。

## <a name="syntax"></a>语法

> **#pragma auto_inline (** [{ **on**  |  **off** }] **)**

## <a name="remarks"></a>备注

若要使用 **auto_inline** 杂注，请将其置于函数定义之前和之后（而不是内部）。 Pragma 会在观察到杂注后的第一个函数定义后立即生效。

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
