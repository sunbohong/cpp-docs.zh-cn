---
description: '了解详细信息：/GUARD (启用防护检查) '
title: /GUARD（启用防护检查）
ms.date: 11/04/2016
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
ms.openlocfilehash: 4f76de815bc10f8e1203510b25b237fe8db93444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191714"
---
# <a name="guard-enable-guard-checks"></a>/GUARD（启用防护检查）

在可执行映像中，为控制流防护检查指定支持。

## <a name="syntax"></a>语法

```
/GUARD:{CF|NO}
```

## <a name="remarks"></a>备注

当指定 /GUARD:CF 时，链接器将修改 .dll 或 .exe 的标头，以指示支持控制流防护 (CFG) 运行时检查。 链接器还会将所需的控制流目标地址数据添加到标头。 默认情况下，禁用 /GUARD:CF。 可以通过使用 /GUARD:NO 显式禁用。 为有效，/GUARD： CF 还要求 [/DYNAMICBASE (使用地址空间布局随机化) ](dynamicbase-use-address-space-layout-randomization.md) 链接器选项，该选项默认处于启用状态。

使用 [/guard： cf](guard-enable-control-flow-guard.md) 选项编译源代码时，编译器将通过检查所有间接调用可能的目标地址来分析控制流。 编译器将插入代码，以验证间接调用指令的目标地址在运行时是否处于已知的目标地址列表中。 支持 CFG 的操作系统将停止未能通过 CFG 运行时检查的程序。 这提高了攻击者使用数据损坏来更改调用目标，以执行恶意代码的难度。

必须对编译器和链接器指定 /GUARD:CF 选项，以创建支持 CFG 的可执行映像。 编译但未使用 /GUARD:CF 链接的代码会产生运行时检查开销，但不会启用 CFG 保护。 将/GUARD： CF 选项指定给 `cl` 命令以便在一步中编译和链接时，编译器会将标志传递到链接器。 在 Visual Studio 中设置 **控制流防护** 属性后，/GUARD： CF 选项将同时传递给编译器和链接器。 当单独编译对象文件或库时，必须在命令中显式指定选项 `link` 。

### <a name="to-set-this-linker-option-in-visual-studio"></a>在 Visual Studio 中设置此链接器选项

1. 打开项目“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 展开 " **配置属性**"、" **链接器**"、" **命令行**"。

1. 在 " **其他选项**" 中，输入 `/GUARD:CF` 。

## <a name="see-also"></a>请参阅

[/guard（启用控制流保护）](guard-enable-control-flow-guard.md)<br/>
[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
