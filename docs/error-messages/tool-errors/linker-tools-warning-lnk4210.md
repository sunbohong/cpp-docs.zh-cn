---
description: 了解详细信息：链接器工具警告 LNK4210
title: 链接器工具警告 LNK4210
ms.date: 11/04/2016
f1_keywords:
- LNK4210
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
ms.openlocfilehash: 7634952df026dc664aed2a2f9625a7380b3a38b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150600"
---
# <a name="linker-tools-warning-lnk4210"></a>链接器工具警告 LNK4210

> 部分 *存在;* 可能有未处理的静态初始值设定项或结束符

## <a name="remarks"></a>备注

一些代码引入了静态初始值设定项或终止符，但 VCRuntime 库启动代码或其等效 (需要运行静态初始值设定项或终结器，) 在应用程序启动时不会运行。 下面是一些需要静态初始值设定项或结束符的代码示例：

- 具有构造函数、析构函数或虚函数表的全局类变量。

- 使用非编译时常数初始化的全局变量。

若要解决此问题，请尝试以下操作之一：

- 删除包含静态初始值设定项的所有代码。

- 请勿使用 [/NOENTRY](../../build/reference/noentry-no-entry-point.md)。 删除/NOENTRY 后，你可能还必须从链接器命令行中删除 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 。

- 如果你的生成使用/MT，请将 libcmt.lib、libvcruntime.lib 和 libucrt.lib 添加到链接器命令行。 如果你的生成使用/MTd，请添加 libcmtd.lib、vcruntimed.lib 和 libucrtd.lib。

- 从/clr： pure 编译移动到/clr 时，从链接器行中删除 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 选项。 这将启用 CRT 初始化，并允许在应用程序启动时执行静态初始值设定项。 **/Clr： pure** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

[/Gs](../../build/reference/gs-buffer-security-check.md)编译器选项需要函数进行初始化 `__security_init_cookie` 。 默认情况下，此初始化在中运行的 VCRuntime 库启动代码中提供 `_DllMainCRTStartup` 。

- 如果你的项目是使用/ENTRY 生成的，且/ENTRY 传递的函数不是 `_DllMainCRTStartup` ，则该函数必须调用 `_CRT_INIT` 以初始化 CRT。 如果 DLL 使用/GS、需要静态初始值设定项，或在 MFC 或 ATL 代码的上下文中调用，则单独调用此调用是不够的。 有关详细信息，请参阅 [dll 和 Visual C++ 运行时库行为](../../build/run-time-library-behavior.md) 。

## <a name="see-also"></a>请参阅

- [设置链接器选项](../../build/reference/linking.md)
