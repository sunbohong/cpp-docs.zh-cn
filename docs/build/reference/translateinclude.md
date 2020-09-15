---
title: '/translateInclude (将 include 指令转换为导入指令) '
description: '使用/translateInclude 编译器选项将可导入标头名称 #include 指令转换为导入标头名称指令。'
ms.date: 09/13/2020
f1_keywords:
- /translateInclude
helpviewer_keywords:
- /translateInclude
- Translate include directives into import directives
ms.openlocfilehash: 0050f2cb117e48d69cf97a587ef128b9b45790af
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079133"
---
# <a name="translateinclude-translate-include-directives-into-import-directives"></a>`/translateInclude` (将 include 指令转换为导入指令) 

通知编译器将 `#include` 可导入标头名称的指令转换为 `import header-name;` 指令，而不是使用文本包含。

## <a name="syntax"></a>语法

> **`/translateInclude`**

## <a name="remarks"></a>备注

**`/translateInclude`** 编译器选项要求使用编译器选项启用实验性模块支持，并 [`/experimental:module`](experimental-module.md) 与[/std： c + + 最新](std-specify-language-standard-version.md)选项一起启用。 从 Visual Studio 2019 版本16.8 开始，此选项可用。

**`/translateInclude`** 选项会有效地进行以下转换，其中，示例 `<vector>` 是可导入的标头单元：

```cpp
#include <vector>
```

编译器将此指令替换为：

```cpp
import <vector> ;
```

在 MSVC 中，可导入的标头单位由 **`/headerUnit`** 引用命名。 有关详细信息，请参阅[ `/headerUnit` (Use HEADER unit IFC) ](headerunit.md)。

### <a name="examples"></a>示例

假设某个项目引用了此表中列出的两个头文件及其标题单元：

| 头文件 | IFC 文件 |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

和 *`.cpp`* 包含标头的源文件

```cpp
#include "utils/util.h"
#include "app/app.h"

int main() { }
```

**`/translateInclude`** 选项允许编译器导入标题单元，而不是再次编译标头。 下面是一个示例命令行，用于转换和的 include 指令以 *`util.h`* *`app.h`* 导入标题单元的导入：

```CMD
cl /IC:\ /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 将 **配置** 下拉箭头设置为 " **所有配置**"。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以添加 *`/translateInclude`* 选项。 然后，选择 **"确定" 或 "** **应用** " 保存所做的更改。

## <a name="see-also"></a>另请参阅

[`/experimental:module` (启用模块支持) ](experimental-module.md)\
[ `/headerUnit` (使用标题单元 IFC) ](headerunit.md)。
[`/module:exportHeader` (创建标题单元) ](module-exportheader.md)\
[`/module:reference` (使用命名模块 IFC) ](module-reference.md)
