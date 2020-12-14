---
description: 了解更多：编译器错误 C3610
title: 编译器错误 C3610
ms.date: 11/04/2016
f1_keywords:
- C3610
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
ms.openlocfilehash: 0fca8f57fcdf2e935620118092708ba1c94f5ec0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223134"
---
# <a name="compiler-error-c3610"></a>编译器错误 C3610

"valuetype"：值类型必须是 "装箱"，才能调用方法 "method"

默认情况下，值类型不在托管堆上。 在从 .NET 运行时类调用方法（如）之前， `Object` 需要将值类型移动到托管堆。

只能使用过时的编译器选项 **/clr： oldSyntax** 来访问 C3610。
