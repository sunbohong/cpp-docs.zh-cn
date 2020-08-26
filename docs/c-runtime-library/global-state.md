---
title: CRT 中的全局状态
ms.date: 04/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: a794f201184c10c11611138d30d14b36b00405a7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845180"
---
# <a name="global-state-in-the-crt"></a>CRT 中的全局状态

 (UCRT 的通用 C 运行时中的一些函数) 使用全局状态。 例如， `setlocale()` 设置整个程序的区域设置，它会影响数字分隔符、文本代码页等。

UCRT 的全局状态不会在应用程序和操作系统之间共享。 例如，如果应用程序调用 `setlocale()` ，则不会影响任何使用 C 运行时的操作系统组件的区域设置，反之亦然。

## <a name="os-specific-versions-of-crt-functions"></a>CRT 函数的特定于 OS 的版本

在 UCRT 中，与全局状态交互的函数具有 "双子" 函数，前缀为 `_o_` 。 例如：

- `setlocale()` 影响特定于应用的全局状态。
- `_o_setlocale()` 影响由所有 OS 组件共享的全局状态，但不影响应用。

这两个 "克隆" 函数的唯一区别在于，当它们读取/写入全局 CRT 状态时，特定于 OS 的版本 (也就是说，以) 开头的版本 `_o_` 将使用全局状态的 os 副本，而不是应用的全局状态副本。

这些函数的 OS 特定版本在中 `ucrt.osmode.lib` 。 例如，特定于 OS 的版本 `setlocale()` 为 `_o_setlocale()`

可通过两种方法将组件的 CRT 状态与应用的 CRT 状态隔离：

- 使用编译器选项/MT 静态链接组件 (release) 或 MTd (调试) 。 有关详细信息，请参阅 [/md、/mt、/ld](../build/reference/md-mt-ld-use-run-time-library.md)。 请注意，静态链接可以大大增加二进制大小。
- 从 Windows 10 20H2 开始，通过动态链接到 CRT 来获取 CRT 状态隔离，但调用 OS 模式导出 (以 _o_) 开头的函数。 若要调用 OS 模式导出，请静态地链接到，但使用链接器选项 `/NODEFAULTLIB:libucrt.lib` (release) 或 (调试来忽略静态 UCRT `/NODEFAULTLIB:libucrtd.lib`) 参阅 [/NODEFAULTLIB (忽略库) ](../build/reference/nodefaultlib-ignore-libraries.md) 获取详细信息。 并将添加 `ucrt.osmode.lib` 到链接器输入中。

> [!Note]
> 在源代码中，编写 `setlocale()` ，而不是 `_o_setlocale()` 。 当你对进行链接时 `ucrt.osmode.lib` ，链接器将自动替换特定于 OS 的函数版本。 也就是说， `setlocale()` 将替换为 `_o_setlocale()` 。

链接 `ucrt.osmode.lib` 不会禁用一些仅在应用模式下可用的 UCRT 调用。 尝试调用这些将导致链接错误。

## <a name="global-state-affected-by-appos-separation"></a>受应用/操作系统隔离影响的全局状态

应用和操作系统状态的隔离影响的全局状态包括：

- [区域设置数据](locale.md)
- 通过[信号](reference/signal.md)设置的信号处理程序
- [终止设置的终止](reference/set-terminate-crt.md)例程
- [errno 和 _doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- [Rand](reference/rand.md)和[srand](reference/srand.md)使用的随机数字生成状态
- 返回用户无需释放的缓冲区的函数： [strtok、wcstok、_mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [Tmpnam、_wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime、_wasctime](reference/asctime-wasctime.md) [gmtime、_gmtime32、_gmtime64](reference/gmtime-gmtime32-gmtime64.md) [_fcvt _ecvt](reference/fcvt.md) [_ecvt](reference/ecvt.md) [strerror、_strerror、_wcserror](reference/strerror-strerror-wcserror-wcserror.md) __wcserror
- _Putch 使用的缓冲区 [_putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) 和 [_set_new_mode](reference/set-new-mode.md)
- [fmode] (text-and-binary-mode-file-i-o.md) 
- [时区信息](time-management.md)

## <a name="see-also"></a>另请参阅

[C 运行时库参考](c-run-time-library-reference.md)
