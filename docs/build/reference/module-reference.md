---
title: '/module：引用 (使用命名模块 IFC) '
description: 使用/module： reference 编译器选项可为指定的标头名称或包含文件创建模块标头单元。
ms.date: 09/13/2020
f1_keywords:
- /module:reference
helpviewer_keywords:
- /module:reference
- Use named module IFC
ms.openlocfilehash: 5f40f6b700c38f3238cc7a621313621085fbc289
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079136"
---
# <a name="modulereference-use-named-module-ifc"></a>`/module:reference` (使用命名模块 IFC) 

通知编译器使用现有的 IFC (*`.ifc`*) 用于当前编译。

## <a name="syntax"></a>语法

> **`/module:reference`** *`module-name=filename`*\
> **`/module:reference`** *`filename`*

### <a name="arguments"></a>参数

*`filename`*\
包含 *IFC 数据*的文件的名称，预生成的模块信息。 若要导入多个模块，请 **`/module:reference`** 为每个文件包含单独的选项。

*`module-name`*\
导出的主模块接口单位名称或完整模块分区名称的有效名称。

## <a name="remarks"></a>备注

**`/module:reference`** 编译器选项要求使用编译器选项启用实验性模块支持，并 [`/experimental:module`](experimental-module.md) 与[/std： c + + 最新](std-specify-language-standard-version.md)选项一起启用。 从 Visual Studio 2019 版本16.8 开始，此选项可用。

如果 **`/module:reference`** 参数不是 *`filename`* ，则在 *`module-name`* 运行时将打开该文件，以验证 *`filename`* 参数是否命名了特定的导入。 在具有许多参数的情况下，它可能会导致运行时性能较慢 **`/module:reference`** 。

*`module-name`* 必须是有效的主模块接口单元名称或完整的模块分区名称。 主模块接口名称的示例包括：

- `M`
- `M.N.O`
- `MyModule`
- `my_module`

完整模块分区名称的示例包括：

- `M:P`
- `M.N.O:P.Q`
- `MyModule:Algorithms`
- `my_module:algorithms`

如果使用创建模块引用，则在 *`module-name`* 编译器遇到此名称的导入时，命令行上的其他模块不会得到搜索。 例如，给定以下命令行：

```cmd
cl ... /experimental:module /module:reference m.ifc /module:reference m=n.ifc
```

在上述情况下，如果编译器发现， `import m;` 则 *`m.ifc`* 不会搜索。

### <a name="examples"></a>示例

此表中列出了三个模块：

| 模块 | IFC 文件 |
|--|--|
| *`M`* | *`m.ifc`* |
| *`M:Part1`* | *`m-part1.ifc`* |
| *`Core.Networking`* | *`Networking.ifc`* |

使用参数的引用选项如下所 *`filename`* 示：

```cmd
cl ... /experimental:module /module:reference m.ifc /module:reference m-part.ifc /module:reference Networking.ifc
```

使用的引用选项 *`module-name=filename`* 可能如下所示：

```cmd
cl ... /experimental:module /module:reference m=m.ifc /module:reference M:Part1=m-part.ifc /module:reference Core.Networking=Networking.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 将 **配置** 下拉箭头设置为 " **所有配置**"。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以添加 *`/module:reference`* 选项及其参数。 然后，选择 **"确定" 或 "** **应用** " 保存所做的更改。

## <a name="see-also"></a>另请参阅

[`/experimental:module` (启用模块支持) ](experimental-module.md)\
[`/headerUnit` (使用标题单元 IFC) ](headerunit.md)\
[`/module:exportHeader` (创建标题单元) ](module-exportheader.md)\
[`/translateInclude` (将 include 指令转换为导入指令) ](translateinclude.md)
