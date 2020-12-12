---
description: '了解详细信息：/diagnostics (编译器诊断选项) '
title: '/diagnostics (编译器诊断选项) '
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 2c34edc0374e59720eb05e97379702833efaa703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201412"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/diagnostics (编译器诊断选项) 

使用 **/diagnostics** 编译器选项来指定错误和警告位置信息的显示。

## <a name="syntax"></a>语法

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>备注

Visual Studio 2017 及更高版本支持此选项。

**/Diagnostics** 编译器选项控制错误和警告信息的显示。

**/Diagnostics：经典** 选项是默认值，它仅报告发现问题的行号。

**/Diagnostics： column** 选项还包含发现问题的列。 这可以帮助你识别导致问题的特定语言构造或字符。

**/Diagnostics：脱字号** 选项包含发现问题的列，并将插入符号 (^) 置于检测到问题的代码行中的位置。

请注意，在某些情况下，编译器不会检测到发生此问题的问题。 例如，在遇到其他意外符号之前，可能不会检测到缺少分号。 将报告列，并且在编译器检测到某个内容错误的位置处放置了插入符号，这并不总是需要进行更正。

从 Visual Studio 2017 开始，可以使用 **/diagnostics** 选项。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的 " **属性页** " 对话框。

1. 在 " **配置属性**" 下，展开 " **c/c + +** " 文件夹，然后选择 " **常规** " 属性页。

1. 使用 " **诊断格式** " 字段中的下拉列表控件选择诊断显示选项。 选择 **"确定" 或 "** **应用** " 保存更改。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
