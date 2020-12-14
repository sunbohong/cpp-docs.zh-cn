---
description: '了解详细信息：/DEFAULTLIB (指定默认库) '
title: /DEFAULTLIB（指定默认库）
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
ms.openlocfilehash: 9abaf158ed01b3e0a04d29c55d213c8749462c43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201685"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB（指定默认库）

指定要搜索的默认库以解析外部引用。

## <a name="syntax"></a>语法

> **/DEFAULTLIB**：_库_

### <a name="arguments"></a>参数

*类库*<br/>
解析外部引用时要搜索的库的名称。

## <a name="remarks"></a>备注

在解析引用时， **/DEFAULTLIB** 选项会将一个 *库* 添加到链接搜索的库的列表中。 在命令行上和在 .obj 文件中命名的默认库之前，将搜索用 **/DEFAULTLIB** 指定的库。

使用不带参数的时， [/NODEFAULTLIB (忽略所有默认库)](nodefaultlib-ignore-libraries.md) 选项将覆盖所有 **/DEFAULTLIB**：*library* 选项。 在两个中同时指定相同的 *库* 名称时， **/NODEFAULTLIB**：*library* 选项将重写 **/DEFAULTLIB**：*library* 。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择“配置属性” > “链接器” > “命令行”属性页    。

1. 在 " **其他选项**" 中，输入要搜索的每个库的 **/DEFAULTLIB**：*library* 选项。 选择“确定”以保存更改  。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

- [MSVC 链接器参考](linking.md)
- [MSVC 链接器选项](linker-options.md)
