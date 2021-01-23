---
description: '详细了解： (C/c + + #include 指令) '
title: '#include 指令 (C/C++)'
ms.date: 01/19/2021
f1_keywords:
- '#include'
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.openlocfilehash: 4ba9b07b77d919e8587fc392518d268b935e0c46
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713618"
---
# <a name="include-directive-cc"></a>`#include` 指令 (C/c + +) 

通知预处理器将指定文件的内容包含在指令出现的位置。

## <a name="syntax"></a>语法

> **`#include "`***路径规范***`"`**\
> **`#include <`***路径规范***`>`**

## <a name="remarks"></a>注解

可以将常数和宏定义组织到 *包含文件* (也称为 *标头文件*) ，然后使用 **`#include`** 指令将它们添加到任何源文件中。 包含文件还可用于合并外部变量和复杂数据类型的声明。 在为此目的而创建的包含文件中，类型只能定义和命名一次。

*路径规范* 是一个文件名，可以选择性地以目录规范开头。 文件名必须命名现有文件。 *路径规范* 的语法取决于编译程序的操作系统。

有关如何在使用编译的 c + + 应用程序中引用程序集的信息 [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) ，请参阅[ `#using` 指令](../preprocessor/hash-using-directive-cpp.md)。

两种语法形式都使 **`#include`** 指令替换为指定文件的全部内容。 这两种形式之间的差异在于路径未完全指定时预处理器搜索的路径的顺序。 下表显示了这两种语法形式之间的差异。

| 语法形式 | 操作 |
|--|--|
| 带引号的形式 | 预处理器按以下顺序搜索包含文件：<br/><br/> 1) 包含语句的文件所在的目录中 **`#include`** 。<br/><br/> 2) 当前打开的包含文件的目录中，以其打开的相反顺序排列。 搜索从父包含文件的目录中开始进行，然后继续向上到任何祖父包含文件的目录。<br/><br/> 3) 沿着每个编译器选项指定的路径 **`/I`** 。<br/><br/> 4) 沿环境变量指定的路径 `INCLUDE` 。 |
| 尖括号形式 | 预处理器按以下顺序搜索包含文件：<br/><br/> 1) 沿着每个编译器选项指定的路径 **`/I`** 。<br/><br/> 2) 在命令行上进行编译时，沿环境变量指定的路径 `INCLUDE` 。 |

只要找到具有给定名称的文件，预处理器就会停止搜索。 如果将包含文件的完整、明确的路径规范括 (`" "`) ，则预处理器只搜索该路径规范并忽略标准目录。

如果用双引号括起来的文件名是不完整路径说明，则预处理器将首先搜索 *父* 文件的目录。 父文件是包含指令的文件 **`#include`** 。 例如，如果将名为 *file2* 的文件包含在名为 *file1* 的文件中，则 *file1* 是父文件。

包含文件可以 *嵌套*： **`#include`** 指令可以出现在由另一个指令命名的文件中 **`#include`** 。 例如， *file2* 可以包括 *file3*。 在这种情况下， *file1* 仍是 *file2* 的父级，但它将是 *file3* 的祖父。

当包含文件嵌套并在命令行上编译时，目录搜索会从父文件的目录开始。 然后，它会遍历所有祖父文件的目录。 即，搜索将相对于包含当前正在处理的源的目录开始。 如果找不到该文件，则搜索会移动到[ `/I` (其他包含目录) ](../build/reference/i-additional-include-directories.md)编译器选项指定的目录。 最后，搜索由环境变量指定的目录 `INCLUDE` 。

在 Visual Studio 开发环境中，将 `INCLUDE` 忽略环境变量。 改为使用 "包含目录" 的 "项目属性" 中指定的值。 有关如何在 Visual Studio 中设置包括目录的详细信息，请参阅 [include](../build/reference/vcpp-directories-property-page.md#directory-types) Directory 和 [其他包含](../build/reference/c-cpp-prop-page.md#additional-include-directories)目录。

此示例使用尖括号显示文件包含：

```C
#include <stdio.h>
```

此示例将名为的文件的内容添加 *`stdio.h`* 到源程序。 尖括号导致预处理器在 `INCLUDE` *`stdio.h`* 搜索由编译器选项指定的目录之后，搜索由的环境变量指定的目录 **`/I`** 。

下一个示例用引号形式显示文件包含：

```C
#include "defs.h"
```

该示例将指定的文件的内容添加 *`defs.h`* 到源程序。 双引号意味着，预处理器将首先搜索包含父源文件的目录。

包含文件的嵌套可扩展至 10 个级别。 完成嵌套的处理后 **`#include`** ，预处理器将继续在原始源文件中插入封闭的父包含文件。

**Microsoft 专用**

若要查找要包含的源文件，预处理器首先搜索由编译器选项指定的目录 **`/I`** 。 如果该 **`/I`** 选项不存在或失败，则预处理器将使用 `INCLUDE` 环境变量在尖括号中查找任何包含文件。 `INCLUDE`环境变量和 **`/I`** 编译器选项可包含多个路径， () 之间用分号分隔 **`;`** 。 如果有多个目录作为选项的一部分出现 **`/I`** ，或者出现在 `INCLUDE` 环境变量中，则预处理器会按照它们的出现顺序搜索它们。

例如，命令

```cmd
CL /ID:\msvc\include myprog.c
```

使预处理器在目录中搜索 *`D:\msvc\include\`* 包含文件（如） *`stdio.h`* 。 命令

```cmd
SET INCLUDE=D:\msvc\include
CL myprog.c
```

具有同样的作用。 如果两组搜索都失败，则会生成严重的编译器错误。

如果为包含文件完全指定了文件名，该包含文件的路径包含冒号 (例如， *`F:\MSVC\SPECIAL\INCL\TEST.H`*) ，则预处理器会遵循该路径。

对于指定为的包含文件 `#include "path-spec"` ，目录搜索从父文件的目录开始，然后在所有祖父文件的目录中继续进行。 也就是说，搜索将相对于包含正在处理的源文件的目录开始。 如果没有祖父文件，但仍找不到该文件，则搜索将继续，就好像文件名括在尖括号中一样。

**结束 Microsoft 专用**

## <a name="see-also"></a>另请参阅

[预处理器指令](../preprocessor/preprocessor-directives.md)\
[`/I` (其他包含目录) ](../build/reference/i-additional-include-directories.md)
