---
description: '详细了解：/FS (强制同步 PDB 写入) '
title: /FS（强制同步 PDB 写入）
ms.date: 11/04/2016
f1_keywords:
- /FS
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
ms.openlocfilehash: 2dcddd046cc7232f40be5a54d73e659ed099e85d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192026"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS（强制同步 PDB 写入）

强制写入程序数据库 (PDB) 文件（通过 [/zi](z7-zi-zi-debug-information-format.md) 或 [/zi](z7-zi-zi-debug-information-format.md)创建）通过 MSPDBSRV.EXE 进行序列化。

## <a name="syntax"></a>语法

```
/FS
```

## <a name="remarks"></a>备注

默认情况下，当指定 **/zi** 或 **/zi** 时，编译器会锁定 PDB 文件以写入类型信息和符号调试信息。 当类型的数目很大时，这可以显著缩短编译器生成类型信息的时间。 如果另一个进程（例如某个防病毒程序）临时锁定了 PDB 文件，则编译器的写入可能失败并可能产生错误。 当 cl.exe 的多个副本访问同一 PDB 文件时，此问题也可能发生。例如，如果您的解决方案具有使用相同的中间目录或输出目录并启用了并行生成的独立项目。 **/Fs** 编译器选项可防止编译器锁定 PDB 文件，并强制写入到 MSPDBSRV.EXE，这会序列化访问。 这可能极大延长生成的时间，并且它无法阻止可能在 cl.exe 的多个实例同时访问 PDB 文件时发生的错误。 建议您更改解决方案，以便让独立项目对单独的中间文件和输出位置进行写入，或者您也可以使其中一个项目依赖于另一个项目来强制序列化项目生成。

默认情况下， [/mp](mp-build-with-multiple-processes.md) 选项启用 **/fs** 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **c/c + +** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 修改 " **附加选项** " 属性以包含 `/FS` ，然后选择 **"确定"**。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
