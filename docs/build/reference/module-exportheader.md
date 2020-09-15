---
title: '/module： exportHeader (创建标题单元) '
description: 使用/module： exportHeader 编译器选项可为指定的标头名称或包含文件创建模块标头单元。
ms.date: 09/13/2020
f1_keywords:
- /module:exportHeader
helpviewer_keywords:
- /module:exportHeader
- Create header units
ms.openlocfilehash: f0c0ce1c593df742af77aa36189df1e89de75b6b
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079134"
---
# <a name="moduleexportheader-create-header-units"></a>`/module:exportHeader` (创建标题单元) 

指示编译器创建由输入参数指定的标头单元。 编译器在 IFC () 文件中生成输出 *`.ifc`* 。

## <a name="syntax"></a>语法

> **`/module:exportHeader`** *`header-name`* \[...]\
> **`/module:exportHeader`** *`filename`* \[...]

### <a name="arguments"></a>参数

*`header-name`*\
要导出的标头文件。 *`header-name`* 参数必须采用与指令的参数相同的形式 `#include` 。

*`filename`*\
要从其创建标题单元的标头文件的相对或绝对路径。

## <a name="remarks"></a>备注

**`/module:exportHeader`** 编译器选项要求使用编译器选项启用实验性模块支持，并 [`/experimental:module`](experimental-module.md) 与[/std： c + + 最新](std-specify-language-standard-version.md)选项一起启用。 从 Visual Studio 2019 版本16.8 开始，此选项可用。

一个 **`/module:exportHeader`** 编译器选项可以指定您的生成所需的标头名称参数数量。 不需要单独指定它们。

默认情况下，编译标题单元时，编译器不会生成对象文件。 若要生成对象文件，请指定 **`/Fo`** 编译器选项。 有关详细信息，请参阅[ `/Fo` (对象文件名) ](fo-object-file-name.md)。

编译器 *`header-name`* 基于包含目录搜索顺序解析，包括您指定的任何。 有关详细信息，请参阅[ `/I` (其他包含目录) ](i-additional-include-directories.md)。

参数的 *`header-name`* 指定方式必须与它在源中的显示方式相同。 参数对 `<` 命令行上的引号规则和和 `>` 运算符非常敏感。 用于生成标题单元（如使用 VS2019 命令提示符）的正确转义的命令 `<vector>` 可能如下所示：

```cmd
cl ... /experimental:module /module:exportHeader "<vector>"
```

生成本地项目标题，如 `"utils/util.h"` ：

```cmd
cl ... /experimental:module /module:exportHeader """util/util.h"""
```

其他命令行处理器中的报价规则可能会有所不同。

使用的 *`header-name`* 形式时 **`/module:exportHeader`** ，您可能会发现使用互补选项非常有用 **`/module:showResolvedHeader`** 。 **`/module:showResolvedHeader`** 选项打印 *`header-name`* 自变量解析到的文件的绝对路径。

**`/module:exportHeader`** 即使在下，也可以一次处理多个输入 **`/MP`** 。 建议使用 **`/module:output <directory>`** 为每个编译创建一个单独的 IFC 文件。

### <a name="examples"></a>示例

对于给定 `"C:\util\util.h"` 的标头和 `"C:\app\app.h"` ，你可以 *`header-name`* 使用以下命令将它们导出为参数：

```cmd
cl /IC:\ /experimental:module /module:exportHeader """util/util.h""" """app/app.h""" /FoC:\obj
```

可以使用以下命令将其导出为 *`filename`* 参数：

```cmd
cl /IC:\ /experimental:module /module:exportHeader C:\util\util.h C:\app\app.h /FoC:\obj
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 将 **配置** 下拉箭头设置为 " **所有配置**"。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以添加 *`/module:exportHeader`* 选项和任何参数。 然后，选择 **"确定" 或 "** **应用** " 保存所做的更改。

## <a name="see-also"></a>另请参阅

[`/experimental:module` (启用模块支持) ](experimental-module.md)\
[`/headerUnit` (使用标题单元 IFC) ](headerunit.md)\
[`/module:reference` (使用命名模块 IFC) ](module-reference.md)\
[`/translateInclude` (将 include 指令转换为导入指令) ](translateinclude.md)
