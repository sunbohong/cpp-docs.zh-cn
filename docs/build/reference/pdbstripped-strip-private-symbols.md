---
description: '了解详细信息：/PDBSTRIPPED (去除私有符号) '
title: /PDBSTRIPPED（去除私有符号）
ms.date: 11/04/2016
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
ms.openlocfilehash: 27e70281ad12f4401ad6557ead9be11a38684472
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226033"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED（去除私有符号）

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>参数

*pdb_file_name*<br/>
链接器创建的去除的程序数据库 (PDB) 的用户指定名称。

## <a name="remarks"></a>备注

使用生成 PDB 文件 ([/debug](debug-generate-debug-info.md)、 [/Z7](z7-zi-zi-debug-information-format.md)、/Zd 或/zi) 的任何编译器或链接器选项生成程序映像时，/PDBSTRIPPED 选项将创建另一个程序数据库 (PDB) 文件。 此 PDB 文件省略您不希望交付给客户的符号。 第二个 PDB 文件将仅包含：

- 公共符号

- 对象文件的列表以及它们所参与的可执行文件的部分

- 帧指针优化 (用于遍历堆栈的) 调试记录的 FPO

去除的 PDB 文件将不包含：

- 类型信息

- 行号信息

- 每对象文件 CodeView 符号，例如函数、局部变量和静态数据的符号

当你使用/PDBSTRIPPED. 时，仍将生成完整的 PDB 文件

如果未创建 PDB 文件，则将忽略/PDBSTRIPPED。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **调试** " 属性页。

1. 修改 " **去除私有符号** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
