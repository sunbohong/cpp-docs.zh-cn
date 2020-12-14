---
description: 了解更多：编译器警告 C4335
title: 编译器警告 C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: fc8f86036a299c41bc0cb1814b98372edc3b4d8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238305"
---
# <a name="compiler-warning-c4335"></a>编译器警告 C4335

检测到 Mac 文件格式：请将源文件转换为 DOS 格式或 UNIX 格式

源文件第一行的行终止字符为 Macintosh 样式 ( "\r" ) 相对于 UNIX ( "\n" ) 或 DOS ( "\r\n" ) 。

此警告总是作为错误发出。  有关如何禁用此警告的信息，请参阅 [警告](../../preprocessor/warning.md) 杂注。  此外，此警告只会针对每个编译单位发出一次。 因此，如果有多个 `#include` 指令指定了 Macintosh 格式的文件，则将只颁发 C4335 一次。

以 Macintosh 格式生成文件的一种方法是使用 Visual Studio 中的 "**文件**" 菜单) 上的 "**高级保存选项**" (。

## <a name="example"></a>示例

下面的示例生成 C4335。

```cpp
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```
