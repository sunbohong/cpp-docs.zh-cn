---
description: '了解详细信息：/TLBOUT (名称。TLB 文件) '
title: /TLBOUT（命名 .TLB 文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
ms.openlocfilehash: 4e99f3b5a036ddbc424732e771f7bab27aeb228d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229998"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT（命名 .TLB 文件）

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>参数

*路径*<br/>
应在其中创建 .tlb 文件的绝对或相对路径规范。

*filename*<br/>
指定由 MIDL 编译器创建的 .tlb 文件的名称。 不采用任何文件扩展名;如果需要 .tlb 扩展名，请指定 *文件名*.tlb。

## <a name="remarks"></a>备注

/TLBOUT 选项指定 .tlb 文件的名称和扩展名。

当链接具有 [module](../../windows/attributes/module-cpp.md) 属性的项目时，MSVC 链接器会调用 MIDL 编译器。

如果未指定/TLBOUT，则 .tlb 文件将从 [/IDLOUT](idlout-name-midl-output-files.md) *文件名* 获取其名称。 如果未指定/IDLOUT，则会将 .tlb 文件称为 vc70。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 **嵌入的 IDL** 属性页。

1. 修改 **类型库** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)<br/>
[/IGNOREIDL (不将属性处理到 MIDL) ](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (指定 MIDL 命令行选项) ](midl-specify-midl-command-line-options.md)<br/>
[生成特性化程序](../../windows/attributes/cpp-attributes-com-net.md)
