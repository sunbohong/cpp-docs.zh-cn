---
description: '了解详细信息：/MIDL (指定 MIDL 命令行选项) '
title: /MIDL（指定 MIDL 命令行选项）
ms.date: 09/05/2018
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
ms.openlocfilehash: 7c3a095e687ebe58db25cc8313569df3ee3a5886
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190635"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL（指定 MIDL 命令行选项）

指定 MIDL 命令行选项的响应文件

## <a name="syntax"></a>语法

> **/MIDL： \@**<em>文件</em>

## <a name="arguments"></a>参数

*file*<br/>
包含 [MIDL 命令行选项](/windows/win32/Midl/general-midl-command-line-syntax)的文件的名称。

## <a name="remarks"></a>备注

要将 IDL 文件转换为 TLB 文件的所有选项都必须在 *文件* 中提供;不能在链接器的命令行上指定 MIDL 命令行选项。 如果未指定/MIDL，则将仅通过 IDL 文件名和其他选项调用 MIDL 编译器。

文件应每行包含一个 MIDL 命令行选项。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 **配置属性**  >  **链接器**  >  **嵌入的 IDL** 属性页。

1. 修改 **MIDL 命令** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)<br/>
[/IDLOUT (命名 MIDL 输出文件) ](idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL (不将属性处理到 MIDL) ](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT (名称。TLB 文件) ](tlbout-name-dot-tlb-file.md)<br/>
[生成特性化程序](../../windows/attributes/cpp-attributes-com-net.md)
