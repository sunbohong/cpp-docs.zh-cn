---
title: 内在 pragma
description: MSVC 内部 pragma 函数用于指定要用作内部函数的支持的内部函数。
ms.date: 01/22/2021
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
helpviewer_keywords:
- intrinsic pragma
- pragma, intrinsic
no-loc:
- pragma
ms.openlocfilehash: 618705c42c20baf2b99f89e138b30d5633b9e592
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713540"
---
# <a name="intrinsic-no-locpragma"></a>`intrinsic` pragma

指定对的参数列表中指定的函数的调用 pragma 是内部的。

## <a name="syntax"></a>语法

> **`#pragma intrinsic(`***function_1* [ **`,`** *function_2* ...]**`)`**

## <a name="remarks"></a>注解

**`intrinsic`** pragma 指示编译器函数具有已知行为。 编译器可以调用函数，并且不将函数调用替换为内联说明（如果将实现更好的性能）。

下面列出了带内部形式的库函数。 一旦 **`intrinsic`** pragma 检测到，它将在包含指定内部函数的第一个函数定义处生效。 该效果将继续到源文件末尾或 `function` pragma 指定相同内部函数的的外观。 在 **`intrinsic`** pragma 全局级别，只能在函数定义之外使用。

以下函数具有内部形式，当你指定时，将使用内部形式的窗体 [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) ：

:::row:::
   :::column span="":::
      [`abs`](../c-runtime-library/reference/abs-labs-llabs-abs64.md)\
      [`_disable`](../intrinsics/disable.md)\
      [`_enable`](../intrinsics/enable.md)\
      [`fabs`](../c-runtime-library/reference/fabs-fabsf-fabsl.md)\
      [`_inp`](../c-runtime-library/inp-inpw-inpd.md)\
      [`_inpw`](../c-runtime-library/inp-inpw-inpd.md)\
   :::column-end:::
   :::column span="":::
      [`labs`](../c-runtime-library/reference/abs-labs-llabs-abs64.md)\
      [`_lrotl`](../c-runtime-library/reference/lrotl-lrotr.md)\
      [`_lrotr`](../c-runtime-library/reference/lrotl-lrotr.md)\
      [`memcmp`](../c-runtime-library/reference/memcmp-wmemcmp.md)\
      [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md)\
   :::column-end:::
   :::column span="":::
      [`memset`](../c-runtime-library/reference/memset-wmemset.md)\
      [`_outp`](../c-runtime-library/outp-outpw-outpd.md)\
      [`_outpw`](../c-runtime-library/outp-outpw-outpd.md)\
      [`_rotl`](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)\
      [`_rotr`](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)\
   :::column-end:::
   :::column span="":::
      [`strcat`](../c-runtime-library/reference/strcat-wcscat-mbscat.md)\
      [`strcmp`](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)\
      [`strcpy`](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)\
      [`strlen`](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
      [`_strset`](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)\
   :::column-end:::
:::row-end:::

使用内部函数的程序速度更快，因为它们没有函数调用的开销。 不过，由于生成了附加代码，这些代码可能会更大。

### <a name="x86-specific-example"></a>x86 特定示例

`_disable`和 `_enable` 内部函数生成内核模式指令以禁用或启用中断，在内核模式驱动程序中可能非常有用。

在命令行中编译以下代码 `cl -c -FAs sample.c` ，并查看 *`sample.asm`* 它们是否转换为 X86 说明 CLI 和 STI：

```cpp
// pragma_directive_intrinsic.cpp
// processor: x86
#include <dos.h>   // definitions for _disable, _enable
#pragma intrinsic(_disable)
#pragma intrinsic(_enable)
void f1(void) {
   _disable();
   // do some work here that should not be interrupted
   _enable();
}
int main() {
}
```

### <a name="intrinsic-floating-point-functions"></a>内部浮点函数

这些浮点函数没有真正的内部形式。 相反，它们具有直接将参数传递到浮点芯片的版本，而不是将其推送到堆栈上：

:::row:::
   :::column span="":::
      [`acos`](../c-runtime-library/reference/acos-acosf-acosl.md)\
      [`asin`](../c-runtime-library/reference/asin-asinf-asinl.md)\
   :::column-end:::
   :::column span="":::
      [`cosh`](../c-runtime-library/reference/cosh-coshf-coshl.md)\
      [`fmod`](../c-runtime-library/reference/fmod-fmodf.md)\
   :::column-end:::
   :::column span="":::
      [`pow`](../c-runtime-library/reference/pow-powf-powl.md)\
      [`sinh`](../c-runtime-library/reference/sinh-sinhf-sinhl.md)\
   :::column-end:::
   :::column span="":::
      [`tanh`](../c-runtime-library/reference/tanh-tanhf-tanhl.md)\
   :::column-end:::
:::row-end:::

当你指定 [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) 和 [`/fp:fast`](../build/reference/fp-specify-floating-point-behavior.md) (或任何包含 **`/Oi`** ： [`/Ox`](../build/reference/ox-full-optimization.md) 、 [`/O1`](../build/reference/o1-o2-minimize-size-maximize-speed.md) 和) 的选项时，这些浮点函数都具有真正的内部形式 [`/O2`](../build/reference/o1-o2-minimize-size-maximize-speed.md) ：

:::row:::
   :::column span="":::
      [`atan`](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)\
      [`atan2`](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)\
      [`cos`](../c-runtime-library/reference/cos-cosf-cosl.md)\
   :::column-end:::
   :::column span="":::
      [`exp`](../c-runtime-library/reference/exp-expf.md)\
      [`log`](../c-runtime-library/reference/log-logf-log10-log10f.md)\
   :::column-end:::
   :::column span="":::
      [`log10`](../c-runtime-library/reference/log-logf-log10-log10f.md)\
      [`sin`](../c-runtime-library/reference/sin-sinf-sinl.md)\
   :::column-end:::
   :::column span="":::
      [`sqrt`](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)\
      [`tan`](../c-runtime-library/reference/tan-tanf-tanl.md)\
   :::column-end:::
:::row-end:::

您可以使用 [`/fp:strict`](../build/reference/fp-specify-floating-point-behavior.md) 或 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 重写真正的内部浮点选项的生成。 在此情况下，函数将生成为库例程，后者将参数直接传递到浮点芯片，而不是将参数推送到程序堆栈。

有关 [`#pragma function`](../preprocessor/function-c-cpp.md) 如何启用和禁用源文本块的内部函数的详细信息和示例，请参阅。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
