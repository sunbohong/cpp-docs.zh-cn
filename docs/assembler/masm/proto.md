---
description: 了解有关以下方面的详细信息： PROTO
title: PROTO
ms.date: 12/06/2019
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 34dbf9d877dbbc52484e45c5f94212108aeacb42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97126004"
---
# <a name="proto"></a>PROTO

原型函数或过程。 可以使用 [INVOKE](invoke.md) 指令通过 PROTO 指令调用函数原型。

## <a name="syntax"></a>语法

> *标签* **PROTO** ⟦*距离*⟧⟦*language-类型*⟧⟦__，__ ⟦*参数*⟧__：__*tag* .。。⟧

### <a name="parameters"></a>parameters

*标识*\
原型函数的名称。

仅 (32 位 MASM 的 *距离*。 ) \
 (在16位内存模型中使用的可选) 用于重写默认值，并指示 **附近** 或 **远端** 调用。

*language-type* (32 仅限位 MASM。 ) \
 (可选) 设置过程和公共符号的调用和命名约定。 支持的约定包括：

- 32位 **平面** 模型： **C**， **STDCALL**

- 16位模型： **C**， **BASIC**， **FORTRAN**， **PASCAL**， **SYSCALL**， **STDCALL**

*参数*\
函数参数的可选名称。

*符*\
函数参数的类型。

*参数* 和 *标记* 参数可以多次出现，每个传递的参数一次。

## <a name="example"></a>示例

此示例显示了一个名为的函数的 **PROTO** 声明 `addup3` ，该函数使用 **临近** 调用来重写过程调用的16位模型默认值，并对堆栈参数和返回值使用 **C** 调用约定。 它采用两个参数：一个 **词** 和一个 **VARARG**。

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>请参阅

[指令参考](directives-reference.md)\
[.模型引用](dot-model.md)\
[MASM BNF 语法](masm-bnf-grammar.md)
