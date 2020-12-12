---
description: '了解详细信息：/WX (将链接器警告视为错误) '
title: /WX（将链接器警告视为错误）
ms.date: 11/04/2016
f1_keywords:
- /WX
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
ms.openlocfilehash: 965c48ff9c9f975350f3c1e54d8090823be8fd2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261029"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX（将链接器警告视为错误）

```
/WX[:NO]
```

## <a name="remarks"></a>备注

/WX 导致在链接器生成警告时不生成任何输出文件。

这类似于针对编译器的 **/wx** (参见 [/w、/W0、/W1、/W2、/W3、/W4、/W1、/W2、/W3、/W4、/Wall、/wd、/we、/wo、/Wv、/Wx (Warning Level)](compiler-option-warning-level.md) 详细信息) 。 但是，为编译指定 **/wx** 并不意味着 **/wx** 也将对链接阶段有效;必须为每个工具明确指定 **/wx** 。

默认情况下， **/wx** 不起作用。 若要将链接器警告视为错误，请指定 **/wx**。 **/Wx： NO** 与不指定 **/wx** 相同。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 点击“命令行”  属性页。

1. 在 " **附加选项** " 框中键入选项。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
