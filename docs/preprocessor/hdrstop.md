---
description: 详细了解 pragma Microsoft c/c + + 中的 hdrstop 指令
title: hdrstop pragma
ms.date: 01/22/2021
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragma, hdrstop
no-loc:
- pragma
ms.openlocfilehash: caeaeb4a44182b6ba2edfa385a1504fde998cc43
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713605"
---
# <a name="hdrstop-no-locpragma"></a>`hdrstop` pragma

使您能够更好地控制预编译文件名称，以及编译状态的保存位置。

## <a name="syntax"></a>语法

> **`#pragma hdrstop`** [ ( "*filename*" ) ]

## <a name="remarks"></a>注解

*Filename* 是要使用或 (创建的预编译头文件的名称，具体取决于 [`/Yu`](../build/reference/yu-use-precompiled-header-file.md) 是否 [`/Yc`](../build/reference/yc-create-precompiled-header-file.md)) 指定了或。 如果 *filename* 不包含路径规范，则假定预编译标头文件位于源文件所在的同一目录中。

如果 C 或 c + + 文件包含 **`hdrstop`** pragma 使用进行编译时的 **`/Yc`** ，则编译器会将编译状态保存到的位置 pragma 。 不保存其后任何代码的编译状态 pragma 。

使用 *filename* 来命名已编译状态保存到的预编译头文件。 **`hdrstop`** 和 *文件名* 之间的空格是可选的。 中指定的文件名 **`hdrstop`** pragma 是字符串，受任何 C 或 c + + 字符串的约束的约束。 特别是，必须用引号将其括起来，并使用转义符 (反斜杠 **`\`**) 来指定目录名称。 例如：

```C
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

预编译标头文件的名称是根据以下规则按优先顺序决定的。

1. 编译器选项的参数 **`/Fp`**

2. *Filename* 参数`#pragma hdrstop`

3. 带有 PCH 扩展的源文件的基名称

如果 **`/Yc`** 和 **`/Yu`** 选项或都 **`hdrstop`** pragma 不指定文件名，则将源文件的基名称用作预编译标头文件的基名称。

还可以使用预处理命令来执行宏替换，如下所示：

```C
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

以下规则控制 **`hdrstop`** pragma 可放置的位置：

- 它必须出现在任何数据或函数声明/定义的外部。

- 必须在源文件而不是头文件中指定它。

## <a name="example"></a>示例

```C
#include <windows.h>                 // Include several files
#include "myhdr.h"

__inline Disp( char *szToDisplay )   // Define an inline function
{
    // ...                           // Some code to display string
}
#pragma hdrstop
```

在此示例中， **`hdrstop`** pragma 显示了两个文件，并定义了一个内联函数。 在第一位置，此位置可能为的奇数位置 pragma 。 不过，请考虑使用手动预编译选项， **`/Yc`** 和 **`/Yu`** ， **`hdrstop`** pragma 使你能够预编译整个源文件，甚至是内联代码。 Microsoft 编译器不会限制您仅预编译数据声明。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
