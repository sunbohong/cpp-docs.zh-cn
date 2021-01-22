---
description: 详细了解如何指定要延迟加载的 Dll
title: 指定要延迟加载的 Dll
ms.date: 01/19/2021
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.openlocfilehash: de8c2e3cb9605cbc6dbc215a0449348c12295c17
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667500"
---
# <a name="specify-dlls-to-delay-load"></a>指定要延迟加载的 Dll

您可以使用链接器选项指定要延迟加载的 Dll [`/delayload:dllname`](delayload-delay-load-import.md) 。 如果不打算使用自己的 helper 函数版本，还必须将程序与 *`delayimp.lib`* 桌面应用程序的 (链接) 或 *`dloadhelper.lib`* (UWP 应用) 。

下面是延迟加载 DLL 的简单示例：

```cpp
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

生成项目的调试版本。 使用调试器逐句通过代码，你会注意 *`user32.dll`* 到只有在调用时才会加载 `MessageBox` 。

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
