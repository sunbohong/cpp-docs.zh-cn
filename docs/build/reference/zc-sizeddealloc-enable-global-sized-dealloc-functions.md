---
description: '了解有关以下内容的详细信息：/Zc： sizedDealloc (启用全局大小的释放函数) '
title: '/Zc： sizedDealloc (启用全局大小的释放函数) '
ms.date: 03/06/2018
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
ms.openlocfilehash: 4e40355dc3c61f725ca9996dc4c91c0604866fe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269063"
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc： sizedDealloc (启用全局大小的释放函数) 

**/Zc： sizedDealloc** 编译器选项告知编译器 `operator delete` `operator delete[]` `size_t` 在对象的大小可用时，优先调用具有类型的第二个参数的全局或函数。 这些函数可以使用 `size_t` 参数优化释放器性能。

## <a name="syntax"></a>语法

> **/Zc： sizedDealloc**[ **-** ]

## <a name="remarks"></a>备注

在 c + + 11 标准版中，你可以定义静态成员函数 `operator delete` 并 `operator delete[]` 采用第二个 `size_t` 参数。 通常，它们与 [运算符新](../../cpp/new-operator-cpp.md) 函数结合使用，以实现更高效的对象分配器和释放函数。 但是，c + + 11 未在全局范围内定义等效的释放函数集。 在 c + + 11 中，具有类型的第二个参数的全局释放函数被 `size_t` 视为位置删除函数。 必须通过传递大小参数来显式调用它们。

C + + 14 标准更改编译器的行为。 当你定义 global `operator delete` 并 `operator delete[]` 采用类型为的第二个参数时 `size_t` ，如果未调用成员范围版本且对象的大小可用，则编译器首选调用这些函数。 编译器会隐式传递 size 参数。 当编译器无法确定要释放的对象的大小时，将调用单个参数版本。 否则，选择要调用的释放函数版本的常用规则仍适用。 可以通过将范围解析运算符附加到 `::` 释放函数调用 () 来显式指定对全局函数的调用。

默认情况下，从 Visual Studio 2015 开始 Visual C++ 将实现此 c + + 14 标准行为。 可以通过设置 **/zc： sizedDealloc** 编译器选项来显式指定此项。 这表示可能存在重大更改。 使用 **/zc： sizedDealloc** 可以保留旧的行为，例如，当你的代码定义使用类型的第二个参数的位置 delete 运算符时 `size_t` 。 具有类型的第二个参数的全局释放函数的默认 Visual Studio 库实现将 `size_t` 调用单个参数版本。 如果代码仅提供单一参数全局运算符 delete []，则全局调整大小的释放函数的默认库实现将调用全局函数。

默认情况下， **/zc： sizedDealloc** 编译器选项处于启用状态。 [/Permissive-](permissive-standards-conformance.md)选项不影响 **/zc： sizedDealloc**。

有关 Visual C++ 中一致性问题的详细信息，请参阅 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 从 " **配置** " 下拉菜单中，选择 " **所有配置**"。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以包括 **/zc： sizedDealloc** 或 **/zc： SizedDealloc** ，然后选择 **"确定"**。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
[/Zc（一致性）](zc-conformance.md)<br/>
