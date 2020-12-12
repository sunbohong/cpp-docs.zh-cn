---
description: '详细了解：/c (编译而无需链接) '
title: /c（在不链接的情况下进行编译）
ms.date: 11/04/2016
f1_keywords:
- /c
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
ms.openlocfilehash: b9dd692dd99cddf63015fe26e37dc54841816f7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179364"
---
# <a name="c-compile-without-linking"></a>/c（在不链接的情况下进行编译）

阻止自动调用链接。

## <a name="syntax"></a>语法

```
/c
```

## <a name="remarks"></a>备注

用 **/c** 进行编译仅创建 .obj 文件。 必须用正确的文件和选项显式调用链接，才能执行生成的链接阶段。

默认情况下，在开发环境中创建的任何内部项目都使用 **/c** 选项。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

- 此选项在开发环境中不可用。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 若要以编程方式设置此编译器选项，请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>。

## <a name="example"></a>示例

以下命令行将首先创建对象文件 .obj 和 SECOND。第三个 .obj 将被忽略。

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

若要创建可执行文件，必须调用 LINK：

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
