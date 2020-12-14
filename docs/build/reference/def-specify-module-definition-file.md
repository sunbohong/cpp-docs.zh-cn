---
description: '了解详细信息：/DEF (指定 Module-Definition 文件) '
title: /DEF（指定模块定义文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
ms.openlocfilehash: 3b9178004621a55f999f7c2636eaa5b697d2de98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201698"
---
# <a name="def-specify-module-definition-file"></a>/DEF（指定模块定义文件）

```
/DEF:filename
```

## <a name="arguments"></a>参数

*filename*<br/>
要传递给链接器)  ( .def 的模块定义文件的名称。

## <a name="remarks"></a>备注

/DEF 选项将模块定义文件 () 传递到链接器。 仅可指定一个 .def 文件来链接。 有关 .def 文件的详细信息，请参阅 [模块定义文件](module-definition-dot-def-files.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **输入** " 属性页。

1. 修改 " **模块定义文件** " 属性。

若要从开发环境中指定 .def 文件，应将它与其他文件一起添加到项目中，然后将该文件指定给/DEF 选项。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
