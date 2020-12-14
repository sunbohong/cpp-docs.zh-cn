---
description: '详细了解：/Fd (程序数据库文件名) '
title: /Fd（程序数据库文件名）
ms.date: 11/04/2016
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
ms.openlocfilehash: 3990cdd6c560dfdeaef7078a29e965831c2a9504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200658"
---
# <a name="fd-program-database-file-name"></a>/Fd（程序数据库文件名）

指定 [/Z7、/zi、/zi (调试信息格式) ](z7-zi-zi-debug-information-format.md)创建的程序数据库 (PDB) 文件的文件名。

## <a name="syntax"></a>语法

```
/Fdpathname
```

## <a name="remarks"></a>备注

如果不使用 **/fd**，PDB 文件名默认为 VC *x* 0 .pdb，其中 *x* 是使用的 Visual C++ 的主版本。

如果指定的路径名称不包括文件名 (路径以反斜杠) 结束，则编译器将在指定的目录中创建一个名为 VC *x* 0 .pdb 的 .pdb 文件。

如果指定不包含扩展名的文件名，则编译器将使用 .pdb 作为扩展。

此选项还将状态 ( .idb) 文件命名为最小重新生成和增量编译。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击“输出文件”  属性页。

1. 修改 " **程序数据库文件名** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>。

## <a name="example"></a>示例

此命令行创建一个名为进程 .pdb 的 .pdb 文件和一个名为 "进程名称" 的 .idb 文件：

```
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP
```

## <a name="see-also"></a>请参阅

[Output-File (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
[指定路径名](specifying-the-pathname.md)
