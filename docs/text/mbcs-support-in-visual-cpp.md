---
description: 了解详细信息： Visual C++ 中的 MBCS 支持
title: Visual C++ 中的 MBCS 支持
ms.date: 11/04/2016
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
ms.openlocfilehash: f216e381db8111c54f30b2c2fe326f4914024956
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207132"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++ 中的 MBCS 支持

在启用了 MBCS 的 Windows 版本上运行时，Visual C++ 开发系统 (包括集成源代码编辑器、调试器和命令行工具) 启用了 MBCS，但内存窗口除外。

内存窗口不将数据的字节解释为 MBCS 字符，即使它可以将这些字节解释为 ANSI 或 Unicode 字符。 ANSI 字符的大小始终为 1 个字节，而 Unicode 字符的大小为 2 个字节。 在 MBCS 中，字符的大小可以是 1 个或 2 个字节，其解释取决于正在使用的代码页。 因此，内存窗口很难可靠地显示 MBCS 字符。 内存窗口无法知道哪些字节是字符的开头。 开发人员可以在 "内存" 窗口中查看字节值，并在表中查找值以确定字符表示形式。 这是可能的，因为开发人员知道基于源代码的字符串的起始地址。

Visual C++ 在适当的位置接受双字节字符。 这包括对话框中的路径名称和文件名以及 Visual C++ 资源编辑器中的文本项 (例如，对话框编辑器中的静态文本和图标编辑器) 中的静态文本项。 此外，预处理器还识别一些双字节指令（例如，语句中的文件名） `#include` ，并识别为 `code_seg` 和 `data_seg` 杂注的参数。 在源代码编辑器中，虽然不在 C/c + + 语言元素 (如变量名) ，但会接受注释和字符串文本中的双字节字符。

## <a name="support-for-the-input-method-editor-ime"></a><a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> 支持输入法编辑器 (IME) 

为使用 MBCS 的东亚市场编写的应用程序 (例如，日本) 通常支持用于输入单字节和双字节字符的 Windows IME。 Visual C++ 开发环境包含对 IME 的完全支持。

日语键盘不直接支持日文汉字字符。 IME 转换拼音字符串，以另一种日本字母表中的一种形式输入 (罗马字、片假名或平假名) 其可能的日文汉字表示形式。 如果存在多义性，则可以从几个替代项中进行选择。 选择了预期的日文汉字字符后，IME 将两 `WM_CHAR` 条消息传递给控制应用程序。

按 ALT + 组合键激活的 IME \` 将显示为一组按钮 (指示器) 和转换窗口。 应用程序将窗口置于文本插入点处。 应用程序必须 `WM_MOVE` `WM_SIZE` 通过重定位转换窗口以符合目标窗口的新位置或大小来处理和消息。

如果希望应用程序的用户能够输入日文汉字字符，则应用程序必须处理 Windows IME 消息。 有关 IME 编程的详细信息，请参阅 [输入法管理器](/windows/win32/intl/input-method-manager)。

## <a name="visual-c-debugger"></a>Visual C++ 调试器

Visual C++ 调试器可以在 IME 消息上设置断点。 此外，"内存" 窗口还可以显示双字节字符。

## <a name="command-line-tools"></a>命令行工具

Visual C++ 的命令行工具（包括编译器、NMAKE 和资源编译器 ( # A0) ）启用了 MBCS。 在编译应用程序的资源时，可以使用资源编译器的/c 选项来更改默认的代码页。

若要更改源代码编译时的默认区域设置，请使用 [#pragma setlocale](../preprocessor/setlocale.md)。

## <a name="graphical-tools"></a>图形工具

Visual C++ 基于 Windows 的工具（如 Spy + + 和资源编辑工具）完全支持 IME 字符串。

## <a name="see-also"></a>请参阅

[支持多字节字符集 (Mbcs) ](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS 编程提示](../text/mbcs-programming-tips.md)
