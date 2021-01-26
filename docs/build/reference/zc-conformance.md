---
title: /Zc（一致性）
description: /Zc 一致性编译器选项启用或禁用对符合或向后兼容的行为的支持。
ms.date: 01/23/2021
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.openlocfilehash: 066e6712b07dbc28e88a7e01a5055dab90289326
ms.sourcegitcommit: 74e58bee5cffb30b66e17be6dbfde2544369638e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "98763885"
---
# <a name="zc-conformance"></a>`/Zc` (一致性) 

您可以使用 **`/Zc`** 编译器选项来指定标准或特定于 Microsoft 的编译器行为。

## <a name="syntax"></a>语法

> **`/Zc:`**_选项_{，_选项_ ...}

可以 **`/Zc`** 在单个编译器选项中设置由逗号分隔的多个选项 **`/Zc`** 。 如果 **`/Zc`** 在同一命令中启用并禁用了某个选项，则将使用最后显示的选项。

## <a name="remarks"></a>备注

当 Visual Studio 实现了与标准不兼容的 C 或 c + + 扩展时，可以使用 **`/Zc`** 一致性选项来指定标准相容或特定于 Microsoft 的行为。 对于某些选项，Microsoft 特定的行为是默认行为，以防止对现有代码进行大规模的重大更改。 在其他情况下，默认值为标准行为，在安全性、性能或兼容性方面的改进超出了重大更改的成本。 在较新版本的 Visual Studio 中，每种一致性选项的默认设置可能会发生变化。 有关每个一致性选项的详细信息，请参阅特定选项的文章。 [`/permissive-`](permissive-standards-conformance.md)编译器选项将默认情况下不设置的一致性选项设置为一致的设置。

下面是 **`/Zc`** 编译器选项：

| 选项 | 行为 |
|--|--|
| [`/Zc:alignedNew`](zc-alignednew.md) | 默认情况下，在 c + + 17) 中启用 c + + 17 双向动态分配 (。 |
| [`/Zc:auto`](zc-auto-deduce-variable-type.md) | 默认情况下，强制实施新的标准 c + + 表示 **`auto`** () 。 |
| [`/Zc:__cplusplus`](zc-cplusplus.md) | 启用 `__cplusplus` 宏，以便在默认情况下报告支持的标准 () 。 |
| [`/Zc:externConstexpr`](zc-externconstexpr.md) | 默认情况下，启用变量的外部链接 **`constexpr`** (关闭) 。 |
| [`/Zc:forScope`](zc-forscope-force-conformance-in-for-loop-scope.md) | 默认情况下，强制实施标准 c + + **`for`** 范围规则 () 。 |
| [`/Zc:hiddenFriend`](zc-hiddenfriend.md) | 强制执行标准 c + + 隐藏的 friend 规则 (隐含 **`/permissive-`**)  |
| [`/Zc:implicitNoexcept`](zc-implicitnoexcept-implicit-exception-specifiers.md) | 默认情况下，启用隐式 **`noexcept`** on 必需函数 () 。 |
| [`/Zc:inline`](zc-inline-remove-unreferenced-comdat.md) | 如果未引用的函数或数据是 COMDAT 或只有默认 (关闭) ，则将其删除。 |
| [`/Zc:noexceptTypes`](zc-noexcepttypes.md) | **`noexcept`** 默认情况下，在 c + + 17 或更高版本中 (启用 c + + 17 规则) 。 |
| [`/Zc:preprocessor`](zc-preprocessor.md) | 默认情况下，使用新的相容预处理器 (关闭，C11/C17) 除外。 |
| [`/Zc:referenceBinding`](zc-referencebinding-enforce-reference-binding-rules.md) | 默认情况下，UDT 暂时不会绑定到 (关闭) 。 |
| [`/Zc:rvalueCast`](zc-rvaluecast-enforce-type-conversion-rules.md) | 强制标准 c + + 显式类型转换规则 (默认关闭) 。 |
| [`/Zc:sizedDealloc`](zc-sizeddealloc-enable-global-sized-dealloc-functions.md) | 默认情况下，启用默认 () 的 c + + 14 全局大小释放函数。 |
| [`/Zc:strictStrings`](zc-strictstrings-disable-string-literal-type-conversion.md) | `char*` `wchar_t*` 默认情况下，禁用 (关闭字符串或转换) 。 |
| [`/Zc:ternary`](zc-ternary.md) | 在默认情况下，对操作数类型强制执行条件运算符规则 (关闭) 。 |
| [`/Zc:threadSafeInit`](zc-threadsafeinit-thread-safe-local-static-initialization.md) | 默认情况下启用线程安全的本地静态初始化 () 。 |
| [`/Zc:throwingNew`](zc-throwingnew-assume-operator-new-throws.md) | **`operator new`** 默认情况下，假定在失败时引发 () 。 |
| [`/Zc:trigraphs`](zc-trigraphs-trigraphs-substitution.md) | 默认情况下启用 trigraphs (已过时，) 。 |
| [`/Zc:twoPhase`](zc-twophase.md) | 默认情况下，使用不一致的模板分析行为 (符合) 。 |
| [`/Zc:wchar_t`](zc-wchar-t-wchar-t-is-native-type.md) | **`wchar_t`** 是本机类型，而不是默认)  (的 typedef。 |

有关 MSVC 中的一致性问题的详细信息，请参阅 [非标准行为](../../cpp/nonstandard-behavior.md)。

## <a name="see-also"></a>另请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)
