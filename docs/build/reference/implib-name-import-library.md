---
description: '了解详细信息：/IMPLIB (名称导入库) '
title: /IMPLIB（命名导入库）
ms.date: 11/04/2016
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
ms.openlocfilehash: 2a5ea590368d1bc3abbecf38845e97a99a0d1f96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191311"
---
# <a name="implib-name-import-library"></a>/IMPLIB（命名导入库）

> /IMPLIB：*文件名*

## <a name="parameters"></a>parameters

*filename*<br/>
用户为导入库指定的名称。 它将替换默认名称。

## <a name="remarks"></a>备注

当生成包含导出的程序时，/IMPLIB 选项将覆盖链接创建的导入库的默认名称。 默认名称是从主输出文件的基名称和扩展名 .lib 组成的。 如果指定了下列一项或多项，则程序将包含导出：

- 源代码中的 [__declspec (dllexport) ](../../cpp/dllexport-dllimport.md) 关键字

- .Def 文件中的[导出](exports.md)语句

- LINK 命令中的 [/export](export-exports-a-function.md) 规范

当未创建导入库时，LINK 将忽略/IMPLIB。 如果未指定任何导出，则 LINK 不创建导入库。 如果在生成中使用了导出文件，LINK 将假设导入库已存在并且不会创建一个。 有关导入库和导出文件的信息，请参阅 [LIB 参考](lib-reference.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **高级** " 属性页。

1. 修改 " **导入库** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
