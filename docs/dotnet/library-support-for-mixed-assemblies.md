---
description: 了解详细信息：库对混合程序集的支持
title: 混合程序集的库支持
ms.date: 09/18/2018
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
ms.openlocfilehash: d20069c2caa1cf46ebdb54907de586630d4ee71c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113709"
---
# <a name="library-support-for-mixed-assemblies"></a>混合程序集的库支持

Visual C++ 支持使用 c + + 标准库、C 运行库 (CRT) 、ATL 以及使用/clr 编译的应用程序的 MFC [ (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)。 这样，使用这些库的现有应用程序也可以使用 .NET Framework 的功能。

> [!IMPORTANT]
> **/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

此支持包括以下 DLL 和导入库：

- 如果用 **/clr** 编译，则为 msvcmrt.lib [d] .lib。 混合程序集链接到此导入库。

此支持提供了几个相关优势：

- CRT 和 c + + 标准库可用于混合代码。 提供的 CRT 和 c + + 标准库不可验证;最终，在使用本机代码时，你的调用仍会路由到同一个 CRT 和 c + + 标准库。

- 更正混合图像中的统一异常处理。

- 混合图像中 c + + 变量的静态初始化。

- 支持托管代码中的每个 AppDomain 和每个进程变量。

- 解决应用于在 Visual Studio 2003 及更早版本中编译的混合 Dll 的加载程序锁问题。

此外，此支持还提供以下限制：

- 对于用 **/clr** 编译的代码，仅支持 CRT DLL 模型。 没有支持 **/clr** 生成的静态 CRT 库。

## <a name="see-also"></a>请参阅

- [混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md)
