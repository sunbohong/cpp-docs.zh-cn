---
description: '了解详细信息：/VERSION (版本信息) '
title: /VERSION（版本信息）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 7c6a27e4829c4acf66db2887e01a147aceb1c5d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176361"
---
# <a name="version-version-information"></a>/VERSION（版本信息）

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>参数

*主要* 和 *次要*<br/>
要在 .exe 或 .dll 文件的标头中的版本号。

## <a name="remarks"></a>备注

/VERSION 选项告知链接器将版本号置于 .exe 或 .dll 文件的标头中。 若要查看/VERSION.，请使用 DUMPBIN [/HEADERS](headers.md) 查看可选标头值的 "图像版本" 字段。

*主要* 和 *次要* 参数是介于0到65535之间的十进制数字。 默认值为0.0 版。

使用 /VERSION 指定的信息不影响您在文件资源管理器中查看应用程序属性时为应用程序显示的版本信息。 该版本信息来自用于生成应用程序的资源文件。 有关详细信息，请参阅 [版本信息编辑器](../../windows/version-information-editor.md) 。

插入版本号的另一种方法是使用 [版本](version-c-cpp.md) module 定义语句。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **常规** " 属性页。

1. 修改 " **版本** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
