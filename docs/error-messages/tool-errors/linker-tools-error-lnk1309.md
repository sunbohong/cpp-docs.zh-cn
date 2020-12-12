---
description: 了解详细信息：链接器工具错误 LNK1309
title: 链接器工具错误 LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: e04498ae5226f748b6ba5cc2ce0cd9340f4547c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193638"
---
# <a name="linker-tools-error-lnk1309"></a>链接器工具错误 LNK1309

> 检测到 *type1* 模块;无效，开关/CLRIMAGETYPE：*type2*

## <a name="remarks"></a>备注

使用 **/CLRIMAGETYPE** 请求了 CLR 映像类型，但链接器未能生成该类型的图像，因为一个或多个模块与该类型不兼容。

例如，如果指定 **/CLRIMAGETYPE： safe** 并且传递使用 **/clr： pure** 生成的模块，则会看到 LNK1309。

在 visual Studio 2015 中不推荐使用 **/clr： pure** 和 **/clr： safe** 编译器选项和支持库，visual studio 2017 中不支持。

如果尝试使用 ptrustu [d] .lib 构建部分受信任的 CLR 纯应用程序，还会看到 LNK1309。 有关如何创建部分受信任的应用程序的信息，请参阅 [如何：通过移除 CRT 库 DLL 上的依赖项来创建部分受信任的应用程序](../../dotnet/create-a-partially-trusted-application.md)。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md) 和 [/CLRIMAGETYPE (指定 Clr 映像的类型) ](../../build/reference/clrimagetype-specify-type-of-clr-image.md)。
