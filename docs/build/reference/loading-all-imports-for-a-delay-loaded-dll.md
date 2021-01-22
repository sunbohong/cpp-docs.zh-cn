---
description: 了解有关加载延迟加载的 DLL 的所有导入的详细信息
title: 加载延迟加载的 DLL 的所有导入
ms.date: 01/19/2021
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.openlocfilehash: b197c50d3b6b68d77dbfccda99e3c2986c515204
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667209"
---
# <a name="load-all-imports-for-a-delay-loaded-dll"></a>加载延迟加载的 DLL 的所有导入

`__HrLoadAllImportsForDll`函数是在中定义的 *`delayhlp.cpp`* ，它通知链接器加载使用 [`/delayload`](delayload-delay-load-import.md) 链接器选项指定的 DLL 中的所有导入。

加载所有导入后，你可以将错误处理放入代码中的一个位置，而不必使用异常处理来处理对导入的实际调用。 它还避免了这样一种情况：在帮助程序代码无法加载导入的情况下，应用程序将无法通过进程进行部分操作。

调用 `__HrLoadAllImportsForDll` 不会更改挂钩和错误处理的行为。 有关详细信息，请参阅 [错误处理和通知](error-handling-and-notification.md)。

传递给的 DLL 名称将 `__HrLoadAllImportsForDll` 与 dll 本身中存储的名称进行比较，并区分大小写。

下面的示例演示如何调用 `__HrLoadAllImportsForDll` ：

```C
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
