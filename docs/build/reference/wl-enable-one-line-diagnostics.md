---
description: '了解详细信息：/WL (启用 One-Line 诊断) '
title: /WL（启用单行诊断）
ms.date: 11/04/2016
f1_keywords:
- /wl
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
ms.openlocfilehash: 032f2c41558c1475be5673d4a69de9ff9b09f323
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258858"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL（启用单行诊断）

将附加信息追加到错误或警告消息。

## <a name="syntax"></a>语法

```
/WL
```

## <a name="remarks"></a>备注

C + + 编译器中的错误和警告消息后面可以跟有新行上默认显示的其他信息。 从命令行进行编译时，可以将额外的信息行追加到错误或警告消息。 如果将生成输出捕获到日志文件，然后处理该日志以查找所有错误和警告，则可能需要这样做。 分号将错误或警告消息与其他行分隔开。

并非所有错误消息和警告消息都有额外的信息。 下面的代码将生成一个包含附加信息行的错误;它可让你在使用 **/WL** 时测试效果。

```cpp
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
