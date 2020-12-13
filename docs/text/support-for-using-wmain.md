---
description: 了解详细信息：支持使用 wmain
title: 支持使用 wmain
ms.date: 11/04/2016
f1_keywords:
- wWinMain
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
ms.openlocfilehash: b6a954ab62c9bc675bd2b71275d615b3ee4c1376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335750"
---
# <a name="support-for-using-wmain"></a>支持使用 wmain

Visual C++ 支持定义 **wmain** 函数并将宽字符自变量传递给 Unicode 应用程序。 使用类似于的格式将形参声明为 **wmain** `main` 。 然后可以将宽字符自变量和宽字符环境指针（可选）传递给该程序。 wmain  的 `argv` 和 `envp` 参数为 `wchar_t*` 类型。 例如：

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> MFC Unicode 应用程序使用 `wWinMain` 作为入口点。 在此示例中， `CWinApp::m_lpCmdLine` 是一个 Unicode 字符串。 请确保设置 `wWinMainCRTStartup` 了 [/ENTRY](../build/reference/entry-entry-point-symbol.md) 链接器选项。

如果程序使用 main  函数，则多字节字符环境由运行时库在程序启动时创建。 环境的宽字符副本仅在需要时创建（如调用 `_wgetenv` 或 `_wputenv` 函数时）。 第一次调用 `_wputenv` 时，或首次调用时， `_wgetenv` 如果 MBCS 环境已存在，则会创建相应的宽字符字符串环境。 然后由全局变量指向该环境 `_wenviron` ，该变量是全局变量的宽字符版本 `_environ` 。 此时，环境的两个副本 (MBCS 和 Unicode) 同时存在，并在程序的整个生命周期内由运行时系统维护。

同样，如果程序使用 wmain  函数，则在程序启动时创建宽字符环境并用 `_wenviron` 全局变量指向该环境。 MBCS (ASCII) 环境是在首次调用 `_putenv` 或时创建的 `getenv` ，并由 `_environ` 全局变量指向。

## <a name="see-also"></a>请参阅

[支持 Unicode](../text/support-for-unicode.md)<br/>
[Unicode 编程摘要](../text/unicode-programming-summary.md)<br/>
[WinMain 函数](/windows/win32/api/winbase/nf-winbase-winmain)
