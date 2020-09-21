---
title: /ERRORREPORT（报告内部链接器错误）
description: 了解如何使用/ERRORREPORT。
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 7d16904da8490018235278347f23e37339739415
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742731"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT（报告内部链接器错误）

**/ERRORREPORT**选项已弃用。 从 Windows Vista 开始，错误报告由 [Windows 错误报告 (WER) ](/windows/win32/wer/windows-error-reporting) 设置控制。

## <a name="syntax"></a>语法

> **/ERRORREPORT：** \[**无** \|**提示符** \|**队列** \|**发送**]

## <a name="remarks"></a>备注

**/ERRORREPORT**参数将被 Windows 错误报告服务设置重写。 如果 Windows 错误报告启用报表，则链接器会自动向 Microsoft 发送内部错误报表。 如果 Windows 错误报告禁用了报表，则不发送任何报表。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目“属性页” **** 对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 打开 "**配置属性**  >  **链接器**  >  **高级**属性" 页。

1. 修改 **错误报告** 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)\
[MSVC 链接器选项](linker-options.md)
