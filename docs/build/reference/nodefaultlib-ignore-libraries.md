---
description: '了解详细信息：/NODEFAULTLIB (忽略库) '
title: /NODEFAULTLIB（忽略库）
ms.date: 03/26/2019
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
ms.openlocfilehash: 1443d7ac1e17d464baa829d8297234ae80f3b998
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196706"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB（忽略库）

> **/NODEFAULTLIB**[__：__*library*]

## <a name="arguments"></a>参数

*类库*<br/>
希望链接器在解析外部引用时忽略的库。

## <a name="remarks"></a>备注

/NODEFAULTLIB 选项通知链接器从其在解析外部引用时搜索的库列表中删除一个或多个默认库。

若要创建不包含对默认库的引用的 .obj 文件，请使用 [/zl (忽略默认库名称) ](zl-omit-default-library-name.md)。

默认情况下，/NODEFAULTLIB 将在解析外部引用时搜索的库列表中删除所有默认库。 可选的 *library* 参数使你可以从其在解析外部引用时搜索的库列表中删除指定的库。 为要排除的每个库指定一个/NODEFAULTLIB 选项。

链接器解析对外部定义的引用，方法是先在显式指定的库中搜索，然后在使用 [/DEFAULTLIB：](defaultlib-specify-default-library.md) 选项指定的默认库中搜索，然后在 .obj 文件中命名的默认库中进行搜索。

/NODEFAULTLIB：在两个中同时指定相同的 *库* 名称时，*库* 将覆盖/DEFAULTLIB：*library* 。

如果在不使用 C 运行时库的情况下使用/NODEFAULTLIB 来生成程序，则可能还必须使用 [/ENTRY](entry-entry-point-symbol.md) 来指定程序中的入口点函数。 有关详细信息，请参阅 [ CRT 库功能](../../c-runtime-library/crt-library-features.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **输入**" 属性页。

1. 选择 " **忽略所有默认库** " 属性。 或者，在 " **忽略特定的默认库** " 属性中指定要忽略的库的分号分隔列表。 " **命令行** " 属性页显示对这些属性所做的更改的影响。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参见 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> 和 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
