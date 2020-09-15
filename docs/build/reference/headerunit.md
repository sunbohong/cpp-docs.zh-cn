---
title: '/headerUnit (使用标题单元 IFC) '
description: 使用/headerUnit 编译器选项可指定要在当前编译中导入的现有 IFC 标头单元。
ms.date: 09/13/2020
f1_keywords:
- /headerUnit
helpviewer_keywords:
- /headerUnit
- Use header unit IFC
ms.openlocfilehash: 2734df728b188dcfbbe5f475cfc67715a070975d
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079138"
---
# <a name="headerunit-use-header-unit-ifc"></a>`/headerUnit` (使用标题单元 IFC) 

通知编译器将 `#include` 可导入标头名称的指令转换为 `import header-name;` 指令，而不是使用文本包含。

## <a name="syntax"></a>语法

> **`/headerUnit`** *`header-filename`*=*`ifc-filename`*

### <a name="arguments"></a>参数

*`header-filename`*\
编译器解析到的文件的名称 `header-name` 。 在编译器中，将 `import header-name ;` 解析 `header-name` 为磁盘上的某些文件。 用于 *`header-filename`* 指定该文件。 一旦匹配，编译器将打开名为的对应 IFC *`ifc-filename`* 以进行导入。

*`ifc-filename`*\
包含 *IFC 数据*的文件的名称，预生成的模块信息。 若要导入多个标头单位，请 **`/headerUnit`** 为每个文件包含单独的选项。

## <a name="remarks"></a>备注

**`/headerUnit`** 编译器选项要求使用编译器选项启用实验性模块支持，并 [`/experimental:module`](experimental-module.md) 与[/std： c + + 最新](std-specify-language-standard-version.md)选项一起启用。 从 Visual Studio 2019 版本16.8 开始，此选项可用。

编译器无法将单个映射 *`header-name`* 到多个 IFC 文件。 虽然 *`header-name`* 可以将多个自变量映射到单个 IFC，但我们不建议这样做。 将 IFC 的内容导入，就好像它只是由指定的标头 *`header-name`* 。

### <a name="examples"></a>示例

假设某个项目引用了此表中列出的两个头文件及其标题单元：

| 头文件 | IFC 文件 |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

用于引用这些特定标头文件的标头单元的编译器选项可能如下例所示：

```CMD
cl ... /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 将 **配置** 下拉箭头设置为 " **所有配置**"。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以添加 *`/headerUnit`* 选项和参数。 然后，选择 **"确定" 或 "** **应用** " 保存所做的更改。

## <a name="see-also"></a>另请参阅

[`/experimental:module` (启用模块支持) ](experimental-module.md)\
[`/module:exportHeader` (创建标题单元) ](module-exportheader.md)\
[`/module:reference` (使用命名模块 IFC) ](module-reference.md)\
[`/translateInclude` (将 include 指令转换为导入指令) ](translateinclude.md)\
