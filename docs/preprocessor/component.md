---
description: 详细了解 pragma Microsoft c/c + + 中的组件指令
title: 组件 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragma, component
no-loc:
- pragma
ms.openlocfilehash: 68a4117439390c6ec978ae9d766efb395a4ceaa4
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712942"
---
# <a name="component-no-locpragma"></a>`component` pragma

控制源文件内浏览信息或依赖项信息的集合。

## <a name="syntax"></a>语法

> **`#pragma component( browser,`** { **`on`** \| **`off`** } \[ **`,`** **`references`** \[ **`,`** *名称* ]] **`)`** \
> **`#pragma component( minrebuild,`** { **`on`** \| **`off`** } **`)`** \
> **`#pragma component( mintypeinfo,`** { **`on`** \| **`off`** } **`)`**

## <a name="remarks"></a>注解

### <a name="browser"></a>浏览器

您可以打开或关闭收集，也可以指定在收集信息时忽略特定名称。

使用 on 或 off 控制今后浏览信息的收集 pragma 。 例如：

```cpp
#pragma component(browser, off)
```

停止编译器收集浏览信息。

> [!NOTE]
> 若要启用此收集浏览信息 pragma ， [必须先启用浏览信息](../build/reference/building-browse-information-files-overview.md)。

**`references`** 选项可与或不带 *name* 参数一起使用。 使用 **`references`** 不带 *名称* 的会打开或关闭引用的收集 (其他浏览信息将继续收集，但) 。 例如：

```cpp
#pragma component(browser, off, references)
```

停止编译器收集引用信息。

使用 **`references`** with *name* 并 **`off`** 防止在 "浏览信息" 窗口中显示引用 *名称* 。 使用此语法可忽略您不感兴趣的名称和类型，并减小浏览信息文件的大小。 例如：

```cpp
#pragma component(browser, off, references, DWORD)
```

忽略从该点开始对 DWORD 值的引用。 你可以使用以下方法来启用对 DWORD 的引用的收集 **`on`** ：

```cpp
#pragma component(browser, on, references, DWORD)
```

这是继续收集 *名称* 引用的唯一方法;您必须显式打开已关闭的任何 *名称* 。

若要防止预处理器展开 *名称* (例如将 NULL 扩展到 0) ，请在其两侧加上引号：

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>最小重新生成

不推荐使用的[ `/Gm` (启用最小重新生成) ](../build/reference/gm-enable-minimal-rebuild.md)功能要求编译器创建和存储 c + + 类依赖关系信息，这会占用磁盘空间。 若要节省磁盘空间，可以 `#pragma component( minrebuild, off )` 在不需要收集依赖项信息时使用，例如，在不变的标头文件中。 `#pragma component( minrebuild, on )`在不变的类后插入，以重新打开依赖项集合。

### <a name="reduce-type-information"></a>减小类型信息

**`mintypeinfo`** 选项可减少指定区域的调试信息。 此信息的量相当大，会影响 .pdb 和 .obj 文件。 无法在区域中调试类和结构 **`mintypeinfo`** 。 使用选项有助于 **`mintypeinfo`** 避免出现以下警告：

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

有关详细信息，请参阅[ `/Gm` (启用最小重新生成) ](../build/reference/gm-enable-minimal-rebuild.md)编译器选项。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
