---
description: '了解详细信息：/INCLUDE (强制符号引用) '
title: /INCLUDE（强制符号引用）
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 4938f5e92f91718f522df103303e6382005d463c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191298"
---
# <a name="include-force-symbol-references"></a>/INCLUDE（强制符号引用）

```
/INCLUDE:symbol
```

## <a name="parameters"></a>parameters

*代号*<br/>
指定要添加到符号表中的符号。

## <a name="remarks"></a>备注

/INCLUDE 选项告知链接器将指定的符号添加到符号表中。

若要指定多个符号，请键入逗号 (、) 、分号 (; ) 或符号名称之间的空格。 在命令行上， `symbol` 为每个符号指定一次/INCLUDE：。

链接器 `symbol` 通过将包含符号定义的对象添加到程序来解析。 此功能可用于包含库对象，否则不会将其链接到程序。

使用此选项指定符号将覆盖由 [/opt： REF](opt-optimizations.md)删除该符号。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **输入** " 属性页。

1. 修改 " **强制符号引用** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
