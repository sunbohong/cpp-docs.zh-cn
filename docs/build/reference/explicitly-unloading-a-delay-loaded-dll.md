---
description: 了解详细信息：显式卸载 Delay-Loaded DLL
title: 显式卸载延迟加载的 DLL
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: 03df08487acc1be05226021d6b7c1593eb0f031b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192377"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>显式卸载延迟加载的 DLL

使用 [/delay](delay-delay-load-import-settings.md)： unload 链接器选项可以卸载延迟加载的 DLL。 默认情况下，当代码使用/delay： unload 和 **__FUnloadDelayLoadedDLL2**) 卸载 (DLL 时，延迟加载的导入将保留在导入地址表 (IAT) 中。 但是，如果在链接器命令行中使用/delay： unload，则 helper 函数将支持显式卸载 DLL，并将 IAT 重置为其原始形式;将覆盖现在无效的指针。 IAT 是 [ImgDelayDescr](calling-conventions-parameters-and-return-type.md) 中的一个字段，其中包含原始 IAT (（如果存在）) 的副本的地址。

## <a name="example"></a>示例

### <a name="code"></a>代码

```
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

- 您可以在 \VC7\INCLUDE\DELAYHLP. 文件中找到 **__FUnloadDelayLoadedDLL2** 函数的实现。.CPP.

- **__FUnloadDelayLoadedDLL2** 函数的 name 参数必须完全匹配 (包括) 导入库包含的大小写 (该字符串也在图像) 的导入表中。 可以通过 [DUMPBIN/DEPENDENTS](dependents.md)查看导入库的内容。 如果需要不区分大小写的字符串匹配，可以将 **__FUnloadDelayLoadedDLL2** 更新为使用其中一个 CRT 字符串函数或 Windows API 调用。

有关详细信息，请参阅 [卸载 Delay-Loaded DLL](unloading-a-delay-loaded-dll.md) 。

## <a name="see-also"></a>请参阅

[Delay-Loaded Dll 的链接器支持](linker-support-for-delay-loaded-dlls.md)
