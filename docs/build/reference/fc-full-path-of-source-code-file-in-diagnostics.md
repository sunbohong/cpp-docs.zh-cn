---
description: '了解详细信息：/FC (诊断中源代码文件的完整路径) '
title: /FC（所诊断源代码文件的完整路径）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 01d1148a32179a7c605a19dc7f2856b7697ae6fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200671"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC（所诊断源代码文件的完整路径）

使编译器在诊断中显示传递给编译器的源代码文件的完整路径。

## <a name="syntax"></a>语法

> /FC

## <a name="remarks"></a>备注

请考虑以下代码示例：

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

如果没有 **/FC**，诊断文本将类似于以下诊断文本：

- compiler_option_FC (5) ：错误 C2143：语法错误： "}" 之前缺少 ";"

对于 **/FC**，诊断文本将类似于以下诊断文本：

- c:\test\ compiler_option_fc .cpp (5) ：错误 C2143：语法错误： "}" 之前缺少 ";"

如果要在使用 &#95;&#95;文件&#95;&#95; 宏时查看文件名的完整路径，也需要 **/FC** 。 有关 &#95;&#95;文件&#95;&#95; 的详细信息，请参阅 [预定义的宏](../../preprocessor/predefined-macros.md) 。

**/Zi** 隐含了 **/FC** 选项。 有关 **/zi** 的详细信息，请参阅 [/Z7、/zi、/Zi (调试信息格式)](z7-zi-zi-debug-information-format.md)。

**/FC** 输出完整路径，用小写。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **高级**" 属性页。

1. 修改 " **使用完整路径** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
