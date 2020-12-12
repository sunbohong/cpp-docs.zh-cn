---
description: '了解详细信息：/OUT (输出文件名) '
title: /OUT（输出文件名）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
ms.openlocfilehash: 1773b4b2dd340bc105495c1b05211c018548976f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226397"
---
# <a name="out-output-file-name"></a>/OUT（输出文件名）

```
/OUT:filename
```

## <a name="arguments"></a>参数

*filename*<br/>
用户为输出文件指定的名称。 它将替换默认名称。

## <a name="remarks"></a>备注

/OUT 选项重写链接器创建的程序的默认名称和位置。

默认情况下，链接器使用指定的第一个 .obj 文件的基名称和相应的扩展名 ( .exe 或 .dll) 来构成文件名。

此选项为 .map 或导入库的默认基名称。 有关详细信息，请参阅 [生成映射](map-generate-mapfile.md) (/MAP) 和 [/IMPLIB](implib-name-import-library.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **常规** " 属性页。

1. 修改 " **输出文件** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
