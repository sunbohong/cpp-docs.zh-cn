---
description: 了解详细信息：链接输出
title: LINK 输出
ms.date: 11/04/2016
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
ms.openlocfilehash: 18d14fda2702e588f69c8a613783087895827826
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190986"
---
# <a name="link-output"></a>LINK 输出

链接输出包含 .exe 文件、Dll、映射文件和消息。

## <a name="output-files"></a><a name="_core_output_files"></a> 输出文件

LINK 的默认输出文件为 .exe 文件。 如果指定了 [/DLL](dll-build-a-dll.md) 选项，则 LINK 生成 .dll 文件。 可以用 [输出文件名 (/out) ](out-output-file-name.md) 选项控制输出文件名。

在增量模式下，LINK 创建 .ilk 文件以保存程序的后续增量生成的状态信息。 有关 .ilk 文件的详细信息，请参阅 [.Ilk 文件](dot-ilk-files-as-linker-input.md)。 有关增量链接的详细信息，请参阅 [/INCREMENTAL) 选项 (增量链接 ](incremental-link-incrementally.md) 。

如果 LINK 创建的程序包含导出 (通常是 DLL) ，则它还会生成 .lib 文件，除非在生成中使用了 .exp 文件。 可以通过 [/IMPLIB](implib-name-import-library.md) 选项控制导入库的文件名。

如果指定了 " [生成映射 (/MAP) ](map-generate-mapfile.md) " 选项，则 LINK 将创建映射。

如果指定了 " [生成调试信息 (/debug) ](debug-generate-debug-info.md) " 选项，则 LINK 将创建一个 PDB 来包含程序的调试信息。

## <a name="other-output"></a><a name="_core_other_output"></a> 其他输出

在不使用 `link` 任何其他命令行输入进行键入时，LINK 将显示汇总其选项的使用情况语句。

LINK 显示版权和版本消息，并回显命令文件输入，除非使用 " [取消显示启动版权标志 (/nologo) ](nologo-suppress-startup-banner-linker.md) " 选项。

您可以使用 " [打印进度" 消息 (/verbose) ](verbose-print-progress-messages.md) "选项显示有关生成的其他详细信息。

以 .LNK *nnnn* 的形式链接问题错误和警告消息。 LIB、DUMPBIN 和 EDITBIN 也使用此错误前缀和数字范围。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
