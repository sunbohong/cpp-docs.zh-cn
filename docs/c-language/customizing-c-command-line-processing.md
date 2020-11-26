---
title: 自定义 C 命令行处理
description: 如何在运行时启动代码中取消 `main` 函数参数和环境参数处理。
ms.date: 11/19/2020
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.openlocfilehash: fc306172491cd401caeecb3c87c0711f8b4ef911
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483290"
---
# <a name="customizing-c-command-line-processing"></a>自定义 C 命令行处理

如果程序不采用命令行参数，则可以取消命令行处理例程来节省少量空间。 若要禁止使用该方法，请在 `/link` 编译器选项或 `LINK` 命令行中包含 `noarg.obj` 文件（用于 `main` 和 `wmain`）。

同样，如果从不通过 `envp` 参数访问环境表，则可以取消内部环境处理例程。 若要禁止使用该方法，请在 `/link` 编译器选项或 `LINK` 命令行中包含 `noenv.obj` 文件（用于 `main` 和 `wmain`）。

有关运行时启动链接器选项的详细信息，请参阅[链接选项](../c-runtime-library/link-options.md)。

程序可以调用 C 运行时库中的 `spawn` 或 `exec` 系列例程。 如果是这样，则不应取消环境处理例程，因为可使用它将环境从父进程传递到子进程中。

## <a name="see-also"></a>另请参阅

[`main` 函数和程序执行](../c-language/main-function-and-program-execution.md)\
[链接选项](../c-runtime-library/link-options.md)。
