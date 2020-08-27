---
title: 清理资源
description: 如何在处理结构化异常处理的终止处理程序期间释放资源。
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: dae92a515db25b9985a890d7d08cc213f88ecfea
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898434"
---
# <a name="cleaning-up-resources"></a>清理资源

在终止处理程序执行期间，你可能不知道在调用终止处理程序之前已获取了哪些资源。 可能会在 **`__try`** 获取所有资源之前中断语句块，以便不会打开所有资源。

为了安全起见，您应该先检查哪些资源已打开，然后再继续处理终止处理。 建议的过程是：

1. 将句柄初始化为 NULL。

1. 在 **`__try`** 语句块中，获取资源。 获取资源时，句柄设置为正值。

1. 在 **`__finally`** 语句块中，释放其对应的句柄或标志变量为非零或非 NULL 的每个资源。

## <a name="example"></a>示例

例如，以下代码使用终止处理程序关闭三个文件并释放内存块。 在语句块中获取了这些资源 **`__try`** 。 在清理资源之前，代码首先检查是否已获取资源。

```cpp
// exceptions_Cleaning_up_Resources.cpp
#include <stdlib.h>
#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void fileOps() {
   FILE  *fp1 = NULL,
         *fp2 = NULL,
         *fp3 = NULL;
   LPVOID lpvoid = NULL;
   errno_t err;

   __try {
      lpvoid = malloc( BUFSIZ );

      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );
      err = fopen_s(&fp3, "CARS.DAT", "w+" );
   }
   __finally {
      if ( fp1 )
         fclose( fp1 );
      if ( fp2 )
         fclose( fp2 );
      if ( fp3 )
         fclose( fp3 );
      if ( lpvoid )
         free( lpvoid );
   }
}

int main() {
   fileOps();
}
```

## <a name="see-also"></a>请参阅

[编写终止处理程序](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
