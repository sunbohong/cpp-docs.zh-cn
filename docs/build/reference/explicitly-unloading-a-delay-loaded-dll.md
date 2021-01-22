---
description: 了解详细信息：显式卸载延迟加载的 DLL
title: 显式卸载延迟加载的 DLL
ms.date: 01/19/2021
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.openlocfilehash: b4e137f293c6497e234a7bb93bd16b5bb6887741
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666883"
---
# <a name="explicitly-unload-a-delay-loaded-dll"></a>显式卸载延迟加载的 DLL

使用 [`/delay:unload`](delay-delay-load-import-settings.md) 链接器选项，你的代码可以显式卸载延迟加载的 DLL。 默认情况下，当代码卸载 DLL 时，延迟加载的导入将保留在导入地址表中 (IAT) 。 但是，如果在 **`/delay:unload`** 链接器命令行中使用，则 helper 函数支持通过调用显式卸载 DLL `__FUnloadDelayLoadedDLL2` ，并将 IAT 重置为其原始形式。 现无效的指针被覆盖。 IAT 是结构中的一个字段 [`ImgDelayDescr`](calling-conventions-parameters-and-return-type.md) ，其中包含原始 IAT 的副本的地址（如果存在）。

## <a name="example"></a>示例

### <a name="code"></a>代码

```C
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

### <a name="comments"></a>注释

有关卸载延迟加载的 DLL 的重要说明：

- 可以在文件中的 `__FUnloadDelayLoadedDLL2` *`delayhlp.cpp`* VC 目录中找到函数的实现 *`include`* 。

- *`name`* 函数的参数 `__FUnloadDelayLoadedDLL2` 必须与 (包括) 导入库包含的大小写完全匹配。  (该字符串也位于图像的导入表中。 ) 可以使用查看导入库的 [`DUMPBIN /DEPENDENTS`](dependents.md) 内容。 如果更愿意使用不区分大小写的字符串匹配，可以更新 `__FUnloadDelayLoadedDLL2` 以使用不区分大小写的 CRT 字符串函数或 WINDOWS API 调用之一。

有关详细信息，请参阅 [卸载延迟加载的 DLL](unloading-a-delay-loaded-dll.md)。

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
