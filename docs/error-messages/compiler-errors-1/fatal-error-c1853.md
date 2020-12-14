---
description: 了解详细信息：严重错误 C1853
title: 错误 C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 60c8e254e9bd36f52bddb4d6dce56c987b6c31e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276226"
---
# <a name="fatal-error-c1853"></a>错误 C1853

> "*filename*" 预编译头文件来自早期版本的编译器，或者预编译头为 c + +，并且你正在使用 c (或反之亦然) 

可能的原因：

- 预编译标头是使用以前的编译器版本编译的。 尝试用当前编译器重新编译标头。

- 预编译标头为 c + +，并且你正在从 C 中使用它。尝试通过指定一个 [/tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 编译器选项或将源文件的后缀更改为 "c"，来重新编译用于 C 的标头。 有关详细信息，请参阅 [预编译代码的两种选择](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code)。
