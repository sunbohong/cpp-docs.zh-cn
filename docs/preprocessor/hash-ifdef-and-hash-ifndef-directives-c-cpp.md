---
description: '了解有关以下内容的详细信息： #ifdef 和 #ifndef 指令 (C/c + +) '
title: '#ifdef 和 #ifndef 指令 (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#ifndef'
- '#ifdef'
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
ms.openlocfilehash: 4888e4516b57465974d99b1c9e8e6393e02f68c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269284"
---
# <a name="ifdef-and-ifndef-directives-cc"></a> (C/c + + 的 #ifdef 和 #ifndef 指令) 

与 **定义** 的运算符一起使用时， **#ifdef** 和 **#ifndef** 指令与 [#if](hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)指令具有相同的效果。

## <a name="syntax"></a>语法

> **#ifdef** *标识符*\
> **#ifndef** *标识符*

这些指令等效于：

> **#if 定义** 的 *标识符*\
> **#if! 已定义** *标识符*

## <a name="remarks"></a>备注

可以使用任意位置的 **#ifdef** 和 **#ifndef** 指令 `#if` 。 如果定义了标识符，则 **#ifdef** *标识符* 语句等效于 `#if 1` 。  它等效于未 `#if 0` 定义 *标识符* ，或未由 `#undef` 指令定义。 这些指令只检查使用 `#define` 定义的标识符是否存在，而不检查在 C 或 C++ 源代码中声明的标识符。

提供这些指令只是为了实现与该语言的早期版本的兼容性。 首选 **(** *标识符* 与指令一起使用 **)** 常数表达式 `#if` 。

**#Ifndef** 指令检查 **#ifdef** 检查的条件的相反情况。 如果尚未定义标识符，或者如果已删除其定义 `#undef` ，则条件为 true (非零) 。 否则，条件为 false (0)。

**Microsoft 专用**

可以使用 [/d](../build/reference/d-preprocessor-definitions.md)选项从命令行传递 *标识符*。 最多可为指定30个宏 `/D` 。

**#Ifdef** 指令对于检查定义是否存在很有用，因为可以从命令行传递定义。 例如：

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[预处理器指令](../preprocessor/preprocessor-directives.md)
