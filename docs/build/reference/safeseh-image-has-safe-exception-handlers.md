---
description: '了解详细信息：/SAFESEH (图像具有安全异常处理程序) '
title: /SAFESEH（图像具有安全异常处理程序）
ms.date: 11/04/2016
f1_keywords:
- /SAFESEH
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
ms.openlocfilehash: 723b5503bca1d98d7df0c638df1dfc8101fc116f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224980"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH（图像具有安全异常处理程序）

```
/SAFESEH[:NO]
```

当指定了 **/SAFESEH** 时，链接器将仅生成一个图像，如果它还可以生成一个映像的安全异常处理程序表。 此表指定操作系统的哪些异常处理程序对图像有效。

仅当链接到 x86 目标时， **/SAFESEH** 才有效。 已记录异常处理程序的平台不支持 **/SAFESEH** 。 例如，在 x64 和 ARM 上，PDATA 中记录了所有异常处理程序。 ML64.exe 支持添加批注，以便将 SEH 信息 (XDATA 和 PDATA) 发送到映像，使你能够通过 ml64.exe 函数展开。 有关详细信息，请参阅 [MASM ( # A0) ](../../assembler/masm/masm-for-x64-ml64-exe.md) 。

如果未指定 **/SAFESEH** ，则链接器将生成一个包含安全异常处理程序表的图像，前提是所有模块都与安全异常处理功能兼容。 如果任何模块都不与安全异常处理功能兼容，则生成的映像将不包含安全异常处理程序表。 如果 [/SUBSYSTEM](subsystem-specify-subsystem.md) 指定 WINDOWSCE 或 EFI_ * 选项之一，则链接器将不会尝试生成包含安全异常处理程序表的映像，因为这些子系统都不能使用该信息。

如果指定了 **/SAFESEH： NO** ，则链接器将不会生成包含安全异常处理程序表的图像，即使所有模块都与安全异常处理功能兼容。

链接器无法生成图像的最常见原因是：) 链接器 (模块中的一个或多个输入文件与安全异常处理程序功能不兼容。 模块与安全异常处理程序不兼容的一个常见原因是，它是使用来自 Visual C++ 早期版本的编译器创建的。

还可以通过使用将函数注册为结构化异常处理程序 [。SAFESEH](../../assembler/masm/dot-safeseh.md)。

不能将现有的二进制文件标记为具有安全异常处理程序， (或不) 异常处理程序;有关安全异常处理的信息必须在生成时添加。

链接器生成安全异常处理程序表的能力取决于使用 C 运行时库的应用程序。 如果与 [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) 链接，并且你想要一个安全异常处理程序表，则需要提供一个加载配置结构， (如可以在 loadcfg CRT 源文件) 中找到，其中包含为 Visual C++ 定义的所有条目。 例如：

```
#include <windows.h>
extern DWORD_PTR __security_cookie;  /* /GS security cookie */

/*
* The following two names are automatically created by the linker for any
* image that has the safe exception table present.
*/

extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is
                                           the count of table entries */
typedef struct {
    DWORD       Size;
    DWORD       TimeDateStamp;
    WORD        MajorVersion;
    WORD        MinorVersion;
    DWORD       GlobalFlagsClear;
    DWORD       GlobalFlagsSet;
    DWORD       CriticalSectionDefaultTimeout;
    DWORD       DeCommitFreeBlockThreshold;
    DWORD       DeCommitTotalFreeThreshold;
    DWORD       LockPrefixTable;            // VA
    DWORD       MaximumAllocationSize;
    DWORD       VirtualMemoryThreshold;
    DWORD       ProcessHeapFlags;
    DWORD       ProcessAffinityMask;
    WORD        CSDVersion;
    WORD        Reserved1;
    DWORD       EditList;                   // VA
    DWORD_PTR   *SecurityCookie;
    PVOID       *SEHandlerTable;
    DWORD       SEHandlerCount;
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;

const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    &__security_cookie,
    __safe_se_handler_table,
    (DWORD)(DWORD_PTR) &__safe_se_handler_count
};
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **链接器** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 在 " **附加选项** " 框中输入选项。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
