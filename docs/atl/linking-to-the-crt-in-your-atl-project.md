---
description: 了解详细信息：链接到 ATL 项目中的 CRT
title: 链接到 ATL 项目中的 CRT
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
ms.openlocfilehash: e54301332d9a83546e41ab42169f06d305bbc6a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147623"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>链接到 ATL 项目中的 CRT

[C Run-Time 库](../c-runtime-library/crt-library-features.md) (CRT) 提供了许多有用的函数，这些函数可在 ATL 开发期间更轻松地进行编程。 所有 ATL 项目都链接到 CRT 库。 你可以在 [用于链接到 CRT 的方法的优点和折衷](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md)中看到链接方法的优点和缺点。

## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>链接到程序图像上的 CRT 的效果

如果以静态方式链接到 CRT，则 CRT 中的代码将放置在可执行文件中，并且无需在系统上提供 CRT DLL 即可运行映像。 如果您动态链接到 CRT，则对 CRT DLL 中的代码的引用会放置在您的图像中，而不是放在代码本身中。 为了使您的映像在给定系统上运行，该系统上必须存在 CRT DLL。 即使在动态链接到 CRT 的情况下，也可能会发现某些代码可以静态链接 (例如 `DllMainCRTStartup`) 。

链接映像时，你可以显式或隐式指定操作系统在加载映像后将调用的入口点。 对于 DLL，默认入口点为 `DllMainCRTStartup` 。 对于 EXE，它是 `WinMainCRTStartup` 。 您可以通过/ENTRY 链接器选项重写默认值。 CRT 为 `DllMainCRTStartup` `WinMainCRTStartup` `wWinMainCRTStartup` EXE) 的 Unicode 入口点提供、和 (实现。 这些 CRT 提供的入口点调用全局对象的构造函数，并初始化某些 CRT 函数使用的其他数据结构。 如果以静态方式链接，此启动代码会将25K 添加到映像。 如果它是动态链接的，则大多数代码都在 DLL 中，因此图像大小始终为小。

有关详细信息，请参阅链接器主题 [/ENTRY (入口点符号) ](../build/reference/entry-entry-point-symbol.md)。

## <a name="optimization-options"></a>优化选项

使用链接器选项/OPT： NOWIN98 可以进一步将默认 ATL 控件降低到10K，同时增加 Windows 98 系统上的加载时间。 有关链接选项的详细信息，请参阅 [/opt (优化) ](../build/reference/opt-optimizations.md)。

## <a name="see-also"></a>请参阅

[用 ATL 和 C Run-Time 代码编程](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL 和 Visual C++ 运行时库行为](../build/run-time-library-behavior.md)
