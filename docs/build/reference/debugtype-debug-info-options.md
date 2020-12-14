---
description: '了解详细信息：/DEBUGTYPE (调试信息选项) '
title: /DEBUGTYPE（调试信息选项）
ms.date: 11/04/2016
f1_keywords:
- /debugtype
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
ms.openlocfilehash: 858d5ed8eb449931229700a10b755dd61ef371cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201724"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE（调试信息选项）

/DEBUGTYPE 选项指定 /DEBUG 选项生成的调试信息的类型。

```
/DEBUGTYPE:[CV | PDATA | FIXUP]
```

## <a name="arguments"></a>参数

**CV**<br/>
指示链接器针对 PDB 文件中的符号、行号和其他对象编译信息发出调试信息。 默认情况下，当指定了 **/debug** 并且未指定 **/DEBUGTYPE** 时，将启用此选项。

**PDATA**<br/>
指示链接器向 PDB 文件中的调试流信息添加 .pdata 和 .xdata 条目。 默认情况下，当同时指定 **/debug** 和 **/DRIVER** 选项时，将启用此选项。 如果 **/DEBUGTYPE： PDATA** 单独指定，则链接器会自动在 PDB 文件中包含调试符号。 如果指定了 **/DEBUGTYPE： PDATA，修正** ，链接器不会在 PDB 文件中包含调试符号。

**FIXUP**<br/>
指示链接器向 PDB 文件中的调试流信息添加重定位表条目。 默认情况下，当同时指定 **/debug** 和 **/PROFILE** 选项时，将启用此选项。 如果指定了 **/DEBUGTYPE：** 或 **/DEBUGTYPE： PDATA，** 则链接器不会在 PDB 文件中包含调试符号。

**/DEBUGTYPE** 的参数可以按任意顺序组合，方法是使用逗号分隔它们。 **/DEBUGTYPE** 选项及其参数不区分大小写。

## <a name="remarks"></a>备注

使用 **/DEBUGTYPE** 选项可以指定在调试流中包含重定位表数据或 pdata 和 xdata 标头信息。 这导致链接器包含有关破坏内核模式代码时内核调试程序中可见的用户模式代码的信息。 若要使调试符号在指定了 **修正** 时可用，请包含 **CV** 参数。

若要在用户模式下调试代码（这对于应用程序来说是典型的），则不需要 **/DEBUGTYPE** 选项。 默认情况下，指定调试输出的编译器开关 ([/Z7、/zi、/zi](z7-zi-zi-debug-information-format.md)) 发出 Visual Studio 调试器所需的所有信息。 使用 **/DEBUGTYPE： PDATA** 或 **/DEBUGTYPE： CV、PDATA、** 对合并用户模式组件和内核模式组件（如设备驱动程序的配置应用）的代码进行修复。 有关内核模式调试程序的详细信息，请参阅 [Windows 调试工具 (WinDbg、KD、CDB、NTSD) ](/windows-hardware/drivers/debugger/index)

## <a name="see-also"></a>请参阅

[/DEBUG (生成调试信息) ](debug-generate-debug-info.md)<br/>
[/DRIVER (Windows NT 内核模式驱动程序) ](driver-windows-nt-kernel-mode-driver.md)<br/>
[/PROFILE (性能工具探查器) ](profile-performance-tools-profiler.md)<br/>
[Windows 调试工具（WinDbg、KD、CDB、NTSD）](/windows-hardware/drivers/debugger/index)
