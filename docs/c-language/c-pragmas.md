---
title: C 杂注
ms.date: 07/26/2020
helpviewer_keywords:
- pragmas, C/C++
ms.assetid: 3d6d36b4-d565-4632-a4cd-e39aeaded5ad
ms.openlocfilehash: ce8efb54eacf40a9feb7b629c2a61a32b3a71b79
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845206"
---
# <a name="c-pragmas"></a>C 杂注

**Microsoft 专用**

“杂注”指示编译器在编译时执行特定操作  。 杂注随编译器的不同而不同。 例如，可以使用 `optimize` pragma 来设置要对程序执行的优化。 Microsoft C 杂注为：

:::row:::
    :::column:::
        [`alloc_text`](../preprocessor/alloc-text.md)\
        [`auto_inline`](../preprocessor/auto-inline.md)\
        [`bss_seg`](../preprocessor/bss-seg.md)\
        [`check_stack`](../preprocessor/check-stack.md)\
        [`code_seg`](../preprocessor/code-seg.md)\
        [`comment`](../preprocessor/comment-c-cpp.md)\
        [`component`](../preprocessor/component.md)\
        [`const_seg`](../preprocessor/const-seg.md)\
        [`data_seg`](../preprocessor/data-seg.md)
    :::column-end:::
    :::column:::
        [`deprecated`](../preprocessor/deprecated-c-cpp.md)\
        [`detect_mismatch`](../preprocessor/detect-mismatch.md)\
        [`fenv_access`](../preprocessor/fenv-access.md)\
        [`float_control`](../preprocessor/float-control.md)\
        [`fp_contract`](../preprocessor/fp-contract.md)\
        [`function`](../preprocessor/function-c-cpp.md)\
        [`hdrstop`](../preprocessor/hdrstop.md)\
        [`include_alias`](../preprocessor/include-alias.md)\
        [`inline_depth`](../preprocessor/inline-depth.md)
    :::column-end:::
    :::column:::
        [`inline_recursion`](../preprocessor/inline-recursion.md)\
        [`intrinsic`](../preprocessor/intrinsic.md)\
        [`make_public`](../preprocessor/make-public.md)\
        [`managed`](../preprocessor/managed-unmanaged.md)\
        [`message`](../preprocessor/message.md)\
        [`omp`](../preprocessor/omp.md)\
        [`once`](../preprocessor/once.md)\
        [`optimize`](../preprocessor/optimize.md)\
        [`pack`](../preprocessor/pack.md)
    :::column-end:::
    :::column:::
        [`pop_macro`](../preprocessor/pop-macro.md)\
        [`push_macro`](../preprocessor/push-macro.md)\
        [`region`, `endregion`](../preprocessor/region-endregion.md)\
        [`runtime_checks`](../preprocessor/runtime-checks.md)\
        [`section`](../preprocessor/section.md)\
        [`setlocale`](../preprocessor/setlocale.md)\
        [`strict_gs_check`](../preprocessor/strict-gs-check.md)\
        [`unmanaged`](../preprocessor/managed-unmanaged.md)\
        [`warning`](../preprocessor/warning.md)
    :::column-end:::
:::row-end:::

有关 Microsoft C 编译器 pragma 的说明，请参阅 [Pragma 指令和 `__Pragma` 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[源文件和源程序](../c-language/source-files-and-source-programs.md)
