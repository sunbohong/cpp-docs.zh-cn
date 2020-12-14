---
description: 了解详细信息： `process`
title: 进程
ms.date: 11/04/2016
f1_keywords:
- process_cpp
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
ms.openlocfilehash: ea5baee65b3375e062939f49bc30f3780c312852
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198591"
---
# `process`

指定托管应用程序进程在该过程中应具有特定全局变量、静态成员变量或在任何应用程序域之间共享的静态局部变量的单一副本。 这主要用于在使用进行编译时使用，在 visual **`/clr:pure`** studio 2015 中已弃用，在 Visual studio 2017 中不受支持。 当使用进行编译时 **`/clr`** ，全局和静态变量默认为每个进程，无需使用 **`__declspec(process)`** 。

只有全局变量、静态成员变量或本机类型的静态局部变量才能用标记 **`__declspec(process)`** 。

**`process`** 仅在用进行编译时有效 [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) 。

如果希望每个应用程序域都有自己的全局变量副本，请使用 [appdomain](../cpp/appdomain.md)。

有关详细信息，请参阅 [应用程序域和 Visual C++](../dotnet/application-domains-and-visual-cpp.md) 。

## <a name="see-also"></a>请参阅

[`__declspec`](../cpp/declspec.md)<br/>
[关键字](../cpp/keywords-cpp.md)
