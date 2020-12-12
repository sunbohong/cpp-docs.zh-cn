---
description: 了解详细信息：。用作链接器输入的 Lib 文件
title: 用作链接器输入的 .Lib 文件
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalDependencies
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
ms.openlocfilehash: f4a3b6c6487947772fb72135fb26f67857f0937e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201256"
---
# <a name="lib-files-as-linker-input"></a>用作链接器输入的 .Lib 文件

LINK 接受 COFF 标准库和 COFF 导入库，这两者通常都具有扩展名 .lib。 标准库包含对象，由 LIB 工具创建。 导入库包含有关其他程序中的导出的信息，并且在生成包含导出或 LIB 工具的程序时通过链接创建。 有关使用 LIB 创建标准或导入库的信息，请参阅 [LIB Reference](lib-reference.md)。 有关使用 LINK 创建导入库的详细信息，请参阅 [/DLL](dll-build-a-dll.md) 选项。

指定库以链接为文件名参数或默认库。 LINK 解析外部引用，方法是在命令行中指定的库中首先搜索，然后在使用 [/DEFAULTLIB](defaultlib-specify-default-library.md) 选项指定的默认库中搜索，然后在 .obj 文件中命名的默认库中进行搜索。 如果使用库名称指定路径，则会在该目录中查找库。 如果未指定路径，则 LINK 首先在运行链接的目录中查找，然后在 LIB 环境变量中指定的任何目录中查找。

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>添加用作开发环境中的链接器输入的 .lib 文件

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**链接器**" 文件夹中的 "**输入**" 属性页。

1. 修改 " **附加依赖项** " 属性以添加 .lib 文件。

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>以编程方式添加用作链接器输入的 .lib 文件

- 请参阅 [AdditionalDependencies](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies)。

## <a name="example"></a>示例

下面的示例演示如何生成和使用 .lib 文件。 首先，生成 .lib 文件：

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

然后，使用刚刚创建的 .lib 文件来编译此示例：

```cpp
// lib_link_input_2.cpp
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp
__declspec(dllimport) int Test();
#include <iostream>
int main() {
   std::cout << Test() << std::endl;
}
```

```Output
213
```

## <a name="see-also"></a>请参阅

[链接输入文件](link-input-files.md)<br/>
[MSVC 链接器选项](linker-options.md)
