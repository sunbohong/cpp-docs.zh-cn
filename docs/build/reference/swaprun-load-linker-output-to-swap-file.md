---
description: '了解详细信息：/SWAPRUN (加载链接器输出以交换文件) '
title: /SWAPRUN（将链接器输出加载到交换文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
ms.openlocfilehash: f62d5e32432a2c738b7782c0fbf0cd4fd76a7f9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230206"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN（将链接器输出加载到交换文件）

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>备注

/SWAPRUN 选项告知操作系统首先将链接器输出复制到交换文件，然后从此处运行映像。 这是 Windows NT 4.0 (及更高版本) 功能。

如果指定 NET，则操作系统将首先将二进制映像从网络复制到交换文件，然后从该文件中加载它。 此选项可用于在网络上运行应用程序。 指定 CD 后，操作系统会将可移动磁盘上的映像复制到页面文件，然后将其加载。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **系统** " 属性页。

1. 修改以下属性之一：

   - **从 CD 交换运行**

   - **从网络交换运行**

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> 和 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> 属性。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
