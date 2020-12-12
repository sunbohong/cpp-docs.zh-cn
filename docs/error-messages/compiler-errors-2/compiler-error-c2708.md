---
description: 了解更多：编译器错误 C2708
title: 编译器错误 C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: c965375c92c98a58a0fb6d0d51b3358e6b5798b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320865"
---
# <a name="compiler-error-c2708"></a>编译器错误 C2708

"identifier"：实参的字节长度不同于以前的调用或引用

[__Stdcall](../../cpp/stdcall.md)函数前面必须有一个原型。 否则，编译器会将对函数的首次调用解释为原型，当编译器遇到不匹配的调用时，将发生此错误。

若要修复此错误，请添加函数原型。
