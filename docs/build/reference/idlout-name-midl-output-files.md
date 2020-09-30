---
title: /IDLOUT（命名 MIDL 输出文件）
ms.date: 11/04/2016
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
ms.openlocfilehash: 8dc26a0564a979c918d1eb1eb85e63e9c73caba0
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506926"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT（命名 MIDL 输出文件）

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>参数

*路径*<br/>
绝对或相对路径规范。 通过指定路径，只会影响 .idl 文件的位置;所有其他文件都放置在项目目录中。

*filename*<br/>
指定由 MIDL 编译器创建的 .idl 文件的名称。 不采用任何文件扩展名;如果希望使用 .idl 扩展名，请指定 *filename*。

## <a name="remarks"></a>注解

/IDLOUT 选项指定 .idl 文件的名称和扩展名。

当链接具有 [module](../../windows/attributes/module-cpp.md) 属性的项目时，MSVC 链接器会调用 MIDL 编译器。

/IDLOUT 还指定与 MIDL 编译器关联的其他输出文件的文件名：

- *filename*.tlb

- *文件名*_p

- *文件名*_i

- *filename*。h

*filename* 是传递给/IDLOUT. 的参数 如果指定了 [/TLBOUT](tlbout-name-dot-tlb-file.md) ，则 .tlb 文件将从/TLBOUT *文件名*获取其名称。

如果既没有指定/IDLOUT 也没有指定/TLBOUT，则链接器将创建 vc70、vc70_p vc70、vc70_i 和 vc70。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹****。

1. 单击 **嵌入的 IDL** 属性页。

1. 修改 " **合并 IDL 基文件名** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)<br/>
[/IGNOREIDL (不将属性处理到 MIDL) ](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (指定 MIDL 命令行选项) ](midl-specify-midl-command-line-options.md)<br/>
[生成特性化程序](../../windows/attributes/cpp-attributes-com-net.md)
