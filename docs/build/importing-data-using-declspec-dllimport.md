---
title: 使用 __declspec(dllimport) 导入数据
description: 如何使用 __declspec(dllimport) 导入 DLL 数据。
ms.date: 09/03/2020
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: cb9850306d6e73b88e2926a6f068ae21f8d32530
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609123"
---
# <a name="importing-data-using-__declspecdllimport"></a>使用 `__declspec(dllimport)` 导入数据

对于数据，使用 `__declspec(dllimport)` 是删除间接寻址层的便捷项。 从 DLL 导入数据时，仍必须浏览导入地址表。 也就是说，在使用 `__declspec(dllimport)` 之前，访问从 DLL 导出的数据时，请务必执行额外级别的间接寻址：

```C
// project.h
// Define PROJECT_EXPORTS when building your DLL
#ifdef PROJECT_EXPORTS   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

然后导出 .DEF 文件中的数据：

```DEF
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

并从 DLL 外部访问它：

```C
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

如果你将数据标记为 `__declspec(dllimport)`，编译器会自动为你生成间接寻址代码。 你不必再担心以上步骤。 如前所述，在生成 DLL 时，不要对数据使用 `__declspec(dllimport)` 声明。 DLL 中的函数不会使用导入地址表来访问数据对象；因此，不会有额外级别的间接寻出现。

若要从 DLL 中自动导出数据，请使用以下声明：

```C
// project.h
// Define PROJECT_EXPORTS when building your DLL
#ifdef PROJECT_EXPORTS   // If accessing the data from inside the DLL
   __declspec(dllexport) ULONG ulDataInDLL;

#else         // If accessing the data from outside the DLL
   __declspec(dllimport) ULONG ulDataInDLL;
#endif
```

## <a name="see-also"></a>请参阅

[导入到应用程序中](importing-into-an-application.md)
