---
description: 了解更多：编译器错误 C2692
title: 编译器错误 C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: 5a9666bf437d65c54d0cb8c460054b2b3ebd0b55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326679"
---
# <a name="compiler-error-c2692"></a>编译器错误 C2692

"function_name"： C 编译器中具有 "/clr" 选项所需的完全原型的函数

在编译 .NET 托管代码时，C 编译器需要 ANSI 函数声明。 此外，如果函数不采用任何参数，它必须显式声明 **`void`** 为参数类型。
