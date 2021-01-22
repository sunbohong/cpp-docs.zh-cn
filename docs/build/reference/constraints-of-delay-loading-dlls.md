---
description: 了解详细信息：延迟加载 Dll 的约束
title: 延迟加载 DLL 的约束
ms.date: 01/19/2021
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.openlocfilehash: 0bc29695aa48fea08a0126d4b814329656a5d3bf
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666974"
---
# <a name="constraints-of-delay-loading-dlls"></a>延迟加载 DLL 的约束

DLL 导入的延迟加载有几个约束。

- 不支持导入数据。 一种解决方法是使用 `LoadLibrary` (或在 `GetModuleHandle` 知道延迟加载帮助程序已将 DLL 加载到) 和后使用来显式处理数据导入 `GetProcAddress` 。

- *`Kernel32.dll`* 不支持延迟加载。 必须加载此 DLL，延迟加载帮助程序例程才能工作。

- 不支持[绑定](binding-imports.md)已转发的入口点。

- 如果 DLL 延迟加载，则进程可能具有不同的行为，而不是在启动时加载。 如果在延迟加载的 DLL 的入口点发生了每个进程初始化，则会出现此情况。 其他情况包括静态 TLS (线程本地存储) ，使用声明， [`__declspec(thread)`](../../cpp/thread.md) 这在通过加载 DLL 时不会得到处理 `LoadLibrary` 。 使用 `TlsAlloc`、`TlsFree`、`TlsGetValue` 和 `TlsSetValue` 的动态 TLS 仍可在静态或者延迟加载的 DLL 中使用。

- 在第一次调用每个函数后，将静态全局函数指针重新初始化为导入的函数。 这是必需的，因为首次使用函数指针将指向 thunk，而不是加载的函数。

- 当前在使用正常导入机制时，没有办法延迟加载 DLL 中的特定过程。

- 自定义调用约定 (如使用 x86 体系结构上的条件代码) 不受支持。 而且，浮点寄存器不会保存在任何平台上。 如果自定义帮助程序例程或挂钩例程使用浮点类型，则需要在使用带有浮点参数的寄存器调用约定的计算机上保存和还原完整的浮点状态。 请注意延迟加载 CRT DLL 的情况，尤其是在调用在 NDP 中使用浮点参数的 CRT 函数时，在帮助函数中 () stack。

## <a name="see-also"></a>另请参阅

[链接器对延迟加载的 Dll 的支持](linker-support-for-delay-loaded-dlls.md)\
[`LoadLibrary` 才能](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)\
[`GetModuleHandle` 才能](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew)\
[`GetProcAddress` 才能](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)\
[`TlsAlloc` 才能](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)\
[`TlsFree` 才能](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree)\
[`TlsGetValue` 才能](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)\
[`TlsSetValue` 函数](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)
