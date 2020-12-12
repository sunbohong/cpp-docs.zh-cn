---
description: '了解详细信息：/IGNOREIDL (Don&#39;t 将属性处理到 MIDL) '
title: '/IGNOREIDL (Don&#39;t 将属性处理到 MIDL) '
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: c68b3ec2f9bd5607ef523667bcddc68b22d3c34c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199813"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don&#39;t 将属性处理到 MIDL) 

```
/IGNOREIDL
```

## <a name="remarks"></a>备注

/IGNOREIDL 选项指定不应将源代码中的任何 [IDL 特性](../../windows/attributes/idl-attributes.md) 处理到 .idl 文件中。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 **嵌入的 IDL** 属性页。

1. 修改 **忽略嵌入的 IDL** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)<br/>
[/IDLOUT (命名 MIDL 输出文件) ](idlout-name-midl-output-files.md)<br/>
[/TLBOUT (名称。TLB 文件) ](tlbout-name-dot-tlb-file.md)<br/>
[/MIDL (指定 MIDL 命令行选项) ](midl-specify-midl-command-line-options.md)<br/>
[生成特性化程序](../../windows/attributes/cpp-attributes-com-net.md)
