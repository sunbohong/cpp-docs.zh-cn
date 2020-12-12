---
description: '了解有关以下内容的详细信息：/Zc： __cplusplus (启用更新 __cplusplus 宏) '
title: /Zc:__cplusplus（启用更新的 __cplusplus 宏）
ms.date: 05/16/2019
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 3aa5579a0315c2bba5e74a8a3c191801328fc589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114671"
---
# <a name="zc__cplusplus-enable-updated-__cplusplus-macro"></a>/Zc:__cplusplus（启用更新的 __cplusplus 宏）

**/Zc： __cplusplus** 编译器选项使 **\_ \_ cplusplus** 预处理器宏能够报告最新 c + + 语言标准支持的更新值。 默认情况下，对于 **\_ \_ cplusplus** 预处理器宏，Visual Studio 始终返回值 "199711L"。

## <a name="syntax"></a>语法

> **/Zc： __cplusplus**[ **-** ]

## <a name="remarks"></a>备注

**\_ \_ Cplusplus** 预处理器宏通常用于报告对特定版本的 c + + 标准的支持。 因为很多现有代码需要此宏的值与“199711L”匹配，所以编译器不会更改此宏的值，除非通过使用 /Zc:__cplusplus 编译器选项进行显式选择。 从 Visual Studio 2017 版本 15.7 开始便已提供 /Zc:__cplusplus 选项，该选项在默认情况下处于禁用状态。 在 visual studio 的早期版本中，如果指定了 **/zc： __cplusplus** ，则 visual studio 将为 **\_ \_ cplusplus** 预处理器宏返回值 "199711L"。 [/permissive-](permissive-standards-conformance.md) 选项不会启用 /Zc:__cplusplus。

启用 **/zc： __cplusplus** 选项后， **\_ \_ cplusplus** 宏报告的值取决于 [/std](std-specify-language-standard-version.md)版本开关设置。 下表列出了该宏的可能值：

|/Zc:__cplusplus 开关|/std:c++ 开关|__cplusplus 值|
|-|-|-|
Zc:__cplusplus|/std:c++14（默认）|201402L
Zc:__cplusplus|/std:c++17|201703L
Zc:__cplusplus|/std:c++latest|201704L
Zc:__cplusplus-（已禁用）|任何值|199711L
未指定|任何值|199711L

编译器不支持 C++98、C++03 或 C++11 的标准切换。

若要更精细地检测对编译器工具集的更改，请使用 [_MSC_VER](../../preprocessor/predefined-macros.md) 预定义宏。 此内置宏的值会随 Visual Studio 2017 和更高版本中的每个工具集更新而增加。 [_MSVC_LANG](../../preprocessor/predefined-macros.md) 预定义宏向标准版本报告 /Zc:__cplusplus 是启用还是禁用状态。 如果启用 /Zc:__cplusplus，则 `__cplusplus == _MSVC_LANG`。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>在 Visual Studio 中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 将 /Zc:__cplusplus 或 /Zc:__cplusplus- 添加到“其他选项:”窗格。

## <a name="see-also"></a>请参阅

- [/Zc（一致性）](zc-conformance.md)
- [/std（指定语言标准版本）](std-specify-language-standard-version.md)
- [预定义宏](../../preprocessor/predefined-macros.md)
