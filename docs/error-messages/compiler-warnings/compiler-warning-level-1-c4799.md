---
description: 了解详细信息：编译器警告 (等级 1) C4799
title: 编译器警告（等级 1）C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: 9bfa84791a713d5ed5c0382402b958c255e30521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334942"
---
# <a name="compiler-warning-level-1-c4799"></a>编译器警告（等级 1）C4799

> 函数 "*function*" 的末尾没有 emm

函数至少具有一个 MMX 指令，但没有 `EMMS` 说明。 使用多媒体指令时， `EMMS` `_mm_empty` 还应使用指令或内部函数清除 MMX 代码末尾的多媒体标记字。

使用 ivec 时，可能会收到 C4799，指示在返回之前，代码不会正确地执行 EMM 指令。 对于这些标头，这是一个错误警告。 可以通过在 IVEC 中定义 _SILENCE_IVEC_C4799 来关闭这些。 但请注意，这也会使编译器无法提供此类型的正确警告。

有关相关信息，请参阅 [Intel 的 MMX 指令集](../../assembler/inline/intel-s-mmx-instruction-set.md)。
