---
description: '了解详细信息：/ORDER (按顺序放置函数) '
title: /ORDER（按顺序放置函数）
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
ms.openlocfilehash: 36888cbb24c869d06eaaa5830b95ae76fc42b860
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226345"
---
# <a name="order-put-functions-in-order"></a>/ORDER（按顺序放置函数）

为单独打包 (COMDAT) 函数指定链接顺序。

## <a name="syntax"></a>语法

> **/Order： \@**<em>filename</em>

### <a name="parameters"></a>parameters

*filename*<br/>
指定 COMDAT 函数的链接顺序的文本文件。

## <a name="remarks"></a>备注

使用 **/order** 编译器选项，可以通过将函数与调用的函数组合在一起来优化程序的分页行为。 你还可以将频繁调用的函数分组在一起。 这些技术称为 *交换优化* 或 *分页优化*，增加了调用的函数在需要时在内存中的可能性，并且无需从磁盘中分页。

当你将源代码编译到对象文件中时，你可以通过使用 [/gy (启用函数级链接)](gy-enable-function-level-linking.md)编译器选项来告知编译器将每个函数置于其自己的部分（称为 *COMDAT*）。 **/Order** 链接器选项通知链接器按指定的顺序将 comdat 放入可执行图像。

若要指定 COMDAT 顺序，请创建一个 *响应文件*，该文件是按名称列出每个 COMDAT 的文本文件（每行一个），并按链接器放置它们的顺序排列。 以 **/order** 选项的 *filename* 参数的形式传递此文件的名称。 对于 c + + 函数，COMDAT 的名称是函数名称的修饰形式。 对于声明为的 c + + 函数，使用 C 函数、和的未修饰名 `main` `extern "C"` 。 函数名称和修饰名区分大小写。 有关修饰名的详细信息，请参阅 [修饰名](decorated-names.md)。

若要查找 Comdat 的修饰名，请使用对象文件上的 [DUMPBIN](dumpbin-reference.md) 工具的 [/SYMBOLS](symbols.md) 选项。 链接器会自动在 **\_** 响应文件中前面加上一个下划线 () 到函数名称，除非该名称以问号 (**？**) 或符号 (**\@**) 。 例如，如果源文件（例如 .cpp）包含函数 `int cpp_func(int)` ， `extern "C" int c_func(int)` `int main(void)` 则该命令将 `DUMPBIN /SYMBOLS example.obj` 列出这些修饰名：

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

在这种情况下，请在响应文件中将名称指定为 `?cpp_func@@YAHH@Z` 、 `c_func` 和 `main` 。

如果链接器选项中显示了多个 **/order** 选项，则指定的最后一个选项生效。

**/Order** 选项禁用增量链接。 如果启用了增量链接，或指定了[/zi (增量 PDB) ](z7-zi-zi-debug-information-format.md)编译器选项，则在指定此选项时，可能会看到链接器警告[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) 。 若要解除此警告，可以使用 [/INCREMENTAL： NO](incremental-link-incrementally.md) 链接器选项关闭增量链接，并使用 [/ZI (生成 pdb) ](z7-zi-zi-debug-information-format.md) 编译器选项生成不带增量链接的 pdb。

> [!NOTE]
> 由于静态函数名称不是公共符号名称，因此 LINK 无法对静态函数进行排序。 指定 **/order** 后，将为顺序响应文件中的每个符号（静态或未找到）生成链接器警告 [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) 。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **优化**" 属性页。

1. 修改 " **函数顺序** " 属性以包含响应文件的名称。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
