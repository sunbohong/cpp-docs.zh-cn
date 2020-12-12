---
description: 了解详细信息：应用程序域和 Visual C++
title: 应用程序域和 Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 55f02aec7b3b2d23f10ae9142dba7c61ff60683f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282817"
---
# <a name="application-domains-and-visual-c"></a>应用程序域和 Visual C++

如果有 `__clrcall` 虚函数，则 vtable 将按应用程序域 (appdomain) 。 如果在一个 appdomain 中创建对象，则只能从该 appdomain 内调用虚拟函数。 在混合模式下 (**/clr**) 如果您的类型没有虚函数，您将拥有每个进程的 vtables `__clrcall` 。 **/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

有关详细信息，请参阅：

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>请参阅

- [混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md)
