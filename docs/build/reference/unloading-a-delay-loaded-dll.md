---
description: 了解有关卸载延迟加载的 DLL 的详细信息
title: 卸载延迟加载的 DLL
ms.date: 01/19/2021
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.openlocfilehash: 2ac898d56609ebb3aadc57ea8df00fa63fcbc3f0
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667242"
---
# <a name="unload-a-delay-loaded-dll"></a>卸载延迟加载的 DLL

默认的延迟加载帮助程序将检查延迟加载描述符是否有一个指针，以及该字段中 (IAT) 的原始导入地址表的副本 `pUnloadIAT` 。 如果是这样，则帮助器将列表中的指针保存到导入延迟描述符。 此项允许 helper 函数按名称查找 DLL，以支持显式卸载该 DLL。

下面是用于显式卸载延迟加载的 DLL 的关联结构和函数：

```cpp
//
// Unload support from delayimp.h
//

// routine definition; takes a pointer to a name to unload

ExternC
BOOL WINAPI
__FUnloadDelayLoadedDLL2(LPCSTR szDll);

// structure definitions for the list of unload records
typedef struct UnloadInfo * PUnloadInfo;
typedef struct UnloadInfo {
    PUnloadInfo     puiNext;
    PCImgDelayDescr pidd;
    } UnloadInfo;

// from delayhlp.cpp
// the default delay load helper places the unloadinfo records in the
// list headed by the following pointer.
ExternC
PUnloadInfo __puiHead;
```

`UnloadInfo`结构是使用 `LocalAlloc` 和实现分别使用和实现的 c + + 类实现的 `LocalFree` `operator new` `operator delete` 。 这些选项保留在一个标准链接列表中，该列表使用 `__puiHead` 作为列表的头。

当你调用时 `__FUnloadDelayLoadedDLL` ，它会尝试查找你在加载的 dll 列表中提供的名称。  (需要完全匹配。 ) 如果找到，则中 IAT 的副本将 `pUnloadIAT` 复制到正在运行的 iat 顶部，以还原 thunk 指针。 然后，将使用释放库 `FreeLibrary` ，匹配的记录与 `UnloadInfo` 列表取消链接并删除，并 `TRUE` 返回。

函数的参数 `__FUnloadDelayLoadedDLL2` 区分大小写。 例如，你可以指定：

```cpp
__FUnloadDelayLoadedDLL2("user32.dll");
```

而不是：

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>另请参阅

[了解 Helper 函数](understanding-the-helper-function.md)
