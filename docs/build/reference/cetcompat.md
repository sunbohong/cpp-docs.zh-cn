---
title: '/CETCOMPAT (CET 阴影堆栈兼容) '
ms.date: 09/01/2020
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 7de7c2007c29769cb3ac8f89d07de8b00bf44c26
ms.sourcegitcommit: e58918c45316d799c1952ca7797a85adbcd0c472
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "89281818"
---
# <a name="cetcompat-cet-shadow-stack-compatible"></a>/CETCOMPAT (CET 阴影堆栈兼容) 

指定是否将可执行映像标记为与控制流强制技术兼容 (CET) 影子堆栈。

## <a name="syntax"></a>语法

> **`/CETCOMPAT`**\
> **`/CETCOMPAT:NO`**

## <a name="arguments"></a>参数

**`NO`**<br/>
指定应将可执行文件标记为与 CET 影子堆栈兼容。

## <a name="remarks"></a>备注

控制流强制技术 (CET) 影子堆栈是一项计算机处理器功能，它提供了一项功能，可防御基于返回的编程 (ROP) 的恶意软件攻击。 有关详细信息，请参阅 [Intel 控制流强制技术预览](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf)。

**`/CETCOMPAT`** 链接器选项告知链接器将二进制文件标记为 CET 影子堆栈兼容。 **`/CETCOMPAT:NO`** 将二进制文件标记为与 CET 影子堆栈不兼容。 如果在命令行上指定了这两个选项，则将使用指定的最后一个选项。 此开关目前仅适用于 x86 和 x64 体系结构。

**`/CETCOMPAT`** 从 Visual Studio 2019 开始，可以使用选项。

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>`/CETCOMPAT`在 Visual Studio 中设置链接器选项

从 Visual Studio 2019 版本16.7 开始：

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **高级**属性" 页。

1. 选择 **CET 影子堆栈兼容** 的属性。

1. 在下拉控件中，选择 **`Yes (/CETCOMPAT)`** 将二进制文件标记为 CET 影子堆栈兼容，或 **`No (/CETCOMPAT:NO)`** 将其标记为不兼容。

在早期版本的 Visual Studio 2019 中：

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **命令行**" 属性页。

1. 在 **其他选项** 编辑控件中，添加 *`/CETCOMPAT`* 以将二进制文件标记为 CET 影子堆栈兼容，或将 *`/CETCOMPAT:NO`* 其显式标记为不兼容。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

此选项不具有编程等效项。

## <a name="see-also"></a>另请参阅

[链接器选项](linker-options.md)
