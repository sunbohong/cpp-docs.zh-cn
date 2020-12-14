---
description: '了解详细信息：/PDB (使用程序数据库) '
title: /PDB（使用程序数据库）
ms.date: 11/04/2016
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
ms.openlocfilehash: 221d5d81dc3578e99751334b2e0a0a61aaaed356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226098"
---
# <a name="pdb-use-program-database"></a>/PDB（使用程序数据库）

```
/PDB:filename
```

## <a name="arguments"></a>参数

*filename*<br/>
 (PDB) 链接器创建的程序数据库的用户指定的名称。 它将替换默认名称。

## <a name="remarks"></a>备注

默认情况下，当指定 [/debug](debug-generate-debug-info.md) 时，链接器会创建一个程序数据库 (PDB) 来保存调试信息。 PDB 的默认文件名具有程序的基名称和扩展名 .pdb。

使用/PDB：*filename* 来指定 PDB 文件的名称。 如果未指定/DEBUG，则忽略/PDB 选项。

PDB 文件最大可为2GB。

有关详细信息，请参阅 [用作链接器输入的 .Pdb 文件](dot-pdb-files-as-linker-input.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **调试** " 属性页。

1. 修改 " **生成程序数据库文件** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
