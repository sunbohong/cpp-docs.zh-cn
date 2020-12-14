---
description: '了解详细信息：/SUBSYSTEM (指定子系统) '
title: /SUBSYSTEM（指定子系统）
ms.date: 11/04/2016
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
ms.openlocfilehash: 18a8ad549cc4aa1e143e43619d549c9eb7ae7324
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236238"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM（指定子系统）

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|
            POSIX|WINDOWS)
            [,major[.minor]]
```

## <a name="arguments"></a>参数

**BOOT_APPLICATION**<br/>
在 Windows 启动环境中运行的应用程序。 有关启动应用程序的详细信息，请参阅 [关于 BCD](/previous-versions/windows/desktop/bcd/about-bcd)。

**CONSOLE**<br/>
Win32 字符模式应用程序。 操作系统提供为控制台应用程序提供控制台。 如果 `main` 为 `wmain` 本机代码定义了或， `int main(array<String ^> ^)` 则为托管代码定义了或，或者使用完全生成应用程序 `/clr:safe` ，控制台是默认值。

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
可扩展固件接口子系统。 有关详细信息，请参阅 EFI 规范。 有关示例，请参阅 Intel 网站。 最低版本和默认版本为1.0。

**本机**<br/>
适用于 Windows NT 的内核模式驱动程序。 此选项通常是为 Windows 系统组件预留的。 如果指定了 [/DRIVER： WDM](driver-windows-nt-kernel-mode-driver.md) ，则默认值为 NATIVE。

**POSIX**<br/>
与 Windows NT 中的 POSIX 子系统一起运行的应用程序。

**WINDOWS**<br/>
应用程序不需要控制台，可能是因为它创建自己的 windows 以便与用户交互。 如果 `WinMain` 为 `wWinMain` 本机代码定义了或，或者 `WinMain(HISTANCE *, HINSTANCE *, char *, int)` 为 `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` 托管代码定义了或，则默认情况下为 WINDOWS。

*主要* 和 *次要*<br/>
 (可选) 指定子系统所需的最低版本。 参数是介于0到65535之间的十进制数字。 有关详细信息，请参阅 "备注"。 版本号没有上限。

## <a name="remarks"></a>备注

**/SUBSYSTEM** 选项为可执行文件指定环境。

子系统的选择会影响链接器将选择的入口点符号 (或入口点函数) 。

子系统的可选最低和默认 *主* 版本号和 *次* 版本号如下所示。

|子系统|最小值|默认|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1.0|1.0|
|CONSOLE|5.01 (x86) 5.02 (x64) 6.02 (ARM) |6.00 (x86、x64) 6.02 (ARM) |
|WINDOWS|5.01 (x86) 5.02 (x64) 6.02 (ARM) |6.00 (x86、x64) 6.02 (ARM) |
|带驱动程序的本机 (： WDM) |1.00 (x86) 1.10 (x64、ARM) |1.00 (x86) 1.10 (x64、ARM) |
|不带/DRIVER 的本机 (： WDM) |4.00 (x86) 5.02 (x64) 6.02 (ARM) |4.00 (x86) 5.02 (x64) 6.02 (ARM) |
|POSIX|1.0|19.90|
|EFI_APPLICATION、EFI_BOOT_SERVICE_DRIVER、EFI_ROM EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择“链接器”文件夹。

1. 选择 " **系统** " 属性页。

1. 修改 `SubSystem` 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
