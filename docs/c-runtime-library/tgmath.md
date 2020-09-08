---
title: 类型-泛型数学
description: 介绍 <t h.> 中的宏，使您可以更轻松地根据参数类型编写调用正确数学函数的 C 代码。
ms.date: 9/3/2020
helpviewer_keywords:
- CRT tgmath.h
ms.openlocfilehash: 8994edcaa05247a16d90b47bca8ec26fca27cda7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89557707"
---
# <a name="type-generic-math"></a>类型-泛型数学

对于 ISO C 标准版 11 (C11) 和更高版本， \<tgmath.h> 除了包含和以外，标头 \<math.h> \<complex.h> 还提供了根据参数类型调用相应数学函数的宏。

C 运行时库数学函数采用实和复杂的形式。 每个变体都具有三种类型，具体取决于参数的类型： `float` 、 `double` 和 `long double` 。 由于 C 不支持重载（如 c + +），因此每个变量都有不同的名称。 例如，若要获取实际浮点值的绝对值，请调用 `fabsf` 、 `fabs` 或， `fabsl` 具体取决于是否要传递 `float` 、 `double` 或 `long double` 值。 若要获取复数绝对值，请调用 `cabsf` 、 `cabs` 或， `cabsl` 具体取决于是否要传递 `float` 、 `double` 和 `long double` 复杂值。 如果参数与以上提到的任何类型都不匹配，则会选择该函数，如同参数已经翻倍。

\<tgmath.h> 包含可简化对要调用的正确数学函数的选择的宏。 宏将检查它们传递到的类型，然后调用正确的函数。 例如，宏将 `sqrt` 绑定 `sqrt(9.9f)` 到 `sqrtf()` ，而它将绑定 `sqrt(9.9)` 到 `sqrt()` 。 如果泛型参数至少有一个宏参数是复杂的，则宏将绑定到复杂函数;否则，它会调用实际函数。

利用中的类型泛型宏 \<tgmath.h> ，你可以编写更易于移植的代码，因为你无需管理强制转换或选择不同的函数名称，具体取决于参数的类型。

这些宏位于其自身的标头中，因此使用标题编写的程序 `<math.h>` 不会中断。 因此， `double x = sin(42);` 其行为与包括时的行为相同 \<math.h> 。 尽管如此，在 \<tgmath.h> 包括标题而不是或的情况下，大多数现有 C 程序都可能会受到影响 \<math.h> \<complex.h> 。

下表列出了中可用的宏 \<tgmath.h> 以及它们所扩展到的内容。 `modf` 不包含在此表中，因为它没有对应的类型通用宏，因为并不清楚如何使其安全，而不会使类型解析复杂化。

|宏  |Real</br>`float`  | Real</br>`double` | Real</br>`long double` | Complex</br>`float` | Complex</br>`double` | Complex</br>`long double` |
|---------|---------|---------|---------|---------|---------|---------|
`acos` | [acosf](reference/mbsnbicmp-mbsnbicmp-l.md) | [acos](reference/mbsnbicmp-mbsnbicmp-l.md) | [acosl](reference/mbsnbicmp-mbsnbicmp-l.md) | [cacosf](reference/cacos-cacosf-cacosl.md) | [cacos](reference/cacos-cacosf-cacosl.md) | [cacosl](reference/cacos-cacosf-cacosl.md) |
`acosh` | [acoshf](reference/acosh-acoshf-acoshl.md) | [acosh](reference/acosh-acoshf-acoshl.md) | [acoshl](reference/acosh-acoshf-acoshl.md) | [cacoshf](reference/cacosh-cacoshf-cacoshl.md) | [cacosh](reference/cacosh-cacoshf-cacoshl.md) | [cacoshl](reference/cacosh-cacoshf-cacoshl.md) |
`asin` | [asinf](reference/asin-asinf-asinl.md) | [asin](reference/asin-asinf-asinl.md) | [asinl](reference/asin-asinf-asinl.md) | [casinf](reference/casin-casinf-casinl.md) | [casin](reference/casin-casinf-casinl.md) | [casinl](reference/casin-casinf-casinl.md) |
`asinh` | [asinhf](reference/asin-asinf-asinl.md) | [asinh](reference/asin-asinf-asinl.md) | [asinhl](reference/asin-asinf-asinl.md) | [casinhf](reference/casinh-casinhf-casinhl.md) | [casinh](reference/casinh-casinhf-casinhl.md) | [casinhl](reference/casinh-casinhf-casinhl.md) |
`atan` | [atanf](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atanl](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [catanf](reference/catan-catanf-catanl.md) | [catan](reference/catan-catanf-catanl.md) | [catanl](reference/catan-catanf-catanl.md) |
`atanh` | [atanhf](reference/atanh-atanhf-atanhl.md) | [atanh](reference/atanh-atanhf-atanhl.md) | [atanhl](reference/atanh-atanhf-atanhl.md) | [catanhf](reference/catanh-catanhf-catanhl.md) | [catanh](reference/catanh-catanhf-catanhl.md) | [catanhl](reference/catanh-catanhf-catanhl.md) |
`cos` | [cosf](reference/cos-cosf-cosl.md) | [缆](reference/cos-cosf-cosl.md) | [cosl](reference/cos-cosf-cosl.md) | [ccosf](reference/ccos-ccosf-ccosl.md) | [ccos](reference/ccos-ccosf-ccosl.md) | [ccosl](reference/ccos-ccosf-ccosl.md) |
`cosh` | [coshf](reference/cosh-coshf-coshl.md) | [cosh](reference/cosh-coshf-coshl.md) | [coshl](reference/cosh-coshf-coshl.md) | [ccoshf](reference/ccosh-ccoshf-ccoshl.md) | [ccosh](reference/ccosh-ccoshf-ccoshl.md) | [ccoshl](reference/ccosh-ccoshf-ccoshl.md) |
`exp` | [expf](reference/exp-expf.md) | [exp](reference/exp-expf.md) | [expl](reference/exp-expf.md) | [cexpf](reference/cexp-cexpf-cexpl.md) | [cexp](reference/cexp-cexpf-cexpl.md) | [cexpl](reference/cexp-cexpf-cexpl.md) |
`fabs` | [fabsf](reference/fabs-fabsf-fabsl.md) | [fabs](reference/fabs-fabsf-fabsl.md) | [fabsl](reference/fabs-fabsf-fabsl.md) | [cabsf](reference/cabs-cabsf-cabsl.md) | [cabs](reference/cabs-cabsf-cabsl.md) | [cabsl](reference/cabs-cabsf-cabsl.md) |
`log` | [logf](reference/log-logf-log10-log10f.md) | [日志](reference/log-logf-log10-log10f.md) | [logl](reference/log-logf-log10-log10f.md) | [clogf](reference/clog-clogf-clogl.md) | [clog](reference/clog-clogf-clogl.md) | [clogl](reference/clog-clogf-clogl.md) |
`pow` | [powf](reference/pow-powf-powl.md) | [pow](reference/pow-powf-powl.md) | [powl](reference/pow-powf-powl.md) | [cpowf](reference/cpow-cpowf-cpowl.md) | [cpow](reference/cpow-cpowf-cpowl.md) | [cpowl](reference/cpow-cpowf-cpowl.md) |
`sin` | [sinf](reference/sin-sinf-sinl.md) | [sin](reference/sin-sinf-sinl.md) | [sinl](reference/sin-sinf-sinl.md) | [csinf](reference/csin-csinf-csinl.md) | [csin](reference/csin-csinf-csinl.md) | [csinl](reference/csin-csinf-csinl.md) |
`sinh` | [sinhf](reference/sinh-sinhf-sinhl.md) | [sinh](reference/sinh-sinhf-sinhl.md) | [sinhl](reference/sinh-sinhf-sinhl.md) | [csinhf](reference/csinh-csinhf-csinhl.md) | [csinh](reference/csinh-csinhf-csinhl.md) | [csinhl](reference/csinh-csinhf-csinhl.md) |
`sqrt` | [sqrtf](reference/sqrt-sqrtf-sqrtl.md) | [sqrt](reference/sqrt-sqrtf-sqrtl.md) | [sqrtl](reference/sqrt-sqrtf-sqrtl.md) | [csqrtf](reference/csqrt-csqrtf-csqrtl.md) | [csqrt](reference/csqrt-csqrtf-csqrtl.md) | [csqrtl](reference/csqrt-csqrtf-csqrtl.md) |
`tan` | [tanf](reference/tan-tanf-tanl.md) | [tan](reference/tan-tanf-tanl.md) | [tanl](reference/tan-tanf-tanl.md) | [ctanf](reference/ctan-ctanf-ctanl.md) | [ctan](reference/ctan-ctanf-ctanl.md) | [ctanl](reference/ctan-ctanf-ctanl.md) |
`tanh` | [tanhf](reference/tanh-tanhf-tanhl.md) | [tanh](reference/tanh-tanhf-tanhl.md) | [tanhl](reference/tanh-tanhf-tanhl.md) | [ctanhf](reference/ctanh-ctanhf-ctanhl.md) | [ctanh](reference/ctanh-ctanhf-ctanhl.md) | [ctanhl](reference/ctanh-ctanhf-ctanhl.md) |
`atan2` | [atan2f](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2l](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | - | - | - |
`cbrt` | [cbrtf](reference/cbrt-cbrtf-cbrtl.md) | [cbrt](reference/cbrt-cbrtf-cbrtl.md) | [cbrtl](reference/cbrt-cbrtf-cbrtl.md) | - | - | - |
`ceil` | [ceilf](reference/ceil-ceilf-ceill.md) | [ceil](reference/ceil-ceilf-ceill.md) | [ceill](reference/ceil-ceilf-ceill.md) | - | - | - |
`copysign` | [copysignf](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [copysign](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [copysignl](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | - | - | - |
`erf` | [erff](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erf](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfl](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`erfc` | [erfcf](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfc](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfcl](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`exp2` | [exp2f](reference/exp2-exp2f-exp2l.md) | [exp2](reference/exp2-exp2f-exp2l.md) | [exp2l](reference/exp2-exp2f-exp2l.md) | - | - | - |
`expm1` | [expm1f](reference/expm1-expm1f-expm1l.md) | [expm1](reference/expm1-expm1f-expm1l.md) | [expm1l](reference/expm1-expm1f-expm1l.md) | - | - | - |
`fdim` | [fdimf](reference/fdim-fdimf-fdiml.md) | [fdim](reference/fdim-fdimf-fdiml.md) | [fdiml](reference/fdim-fdimf-fdiml.md) | - | - | - |
`floor` | [floorf](reference/floor-floorf-floorl.md) | [floor](reference/floor-floorf-floorl.md) | [floorl](reference/floor-floorf-floorl.md) | - | - | - |
`fma` | [fmaf](reference/fma-fmaf-fmal.md) | [fma](reference/fma-fmaf-fmal.md) | [fmal](reference/fma-fmaf-fmal.md) | - | - | - |
`fmax` | [fmaxf](reference/fmax-fmaxf-fmaxl.md) | [fmax](reference/fmax-fmaxf-fmaxl.md) | [fmaxl](reference/fmax-fmaxf-fmaxl.md) | - | - | - |
`fmin` | [fminf](reference/fmin-fminf-fminl.md) | [fmin](reference/fmin-fminf-fminl.md) | [fminl](reference/fmin-fminf-fminl.md) | - | - | - |
`fmod` | [fmodf](reference/fmod-fmodf.md) | [fmod](reference/fmod-fmodf.md) | [fmodl](reference/fmod-fmodf.md) | - | - | - |
`frexp` | [frexpf](reference/frexp.md) | [frexp](reference/frexp.md) | [frexpl](reference/frexp.md) | - | - | - |
`hypot` | [hypotf](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypot](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypotl](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | - | - | - |
`ilogb` | [ilogbf](reference/ilogb-ilogbf-ilogbl2.md) | [ilogb](reference/ilogb-ilogbf-ilogbl2.md) | [ilogbl](reference/ilogb-ilogbf-ilogbl2.md) | - | - | - |
`ldexp` | [ldexpf](reference/ldexp.md) | [ldexp](reference/ldexp.md) | [ldexpl](reference/ldexp.md) | - | - | - |
`lgamma` | [lgammaf](reference/lgamma-lgammaf-lgammal.md) | [lgamma](reference/lgamma-lgammaf-lgammal.md) | [lgammal](reference/lgamma-lgammaf-lgammal.md) | - | - | - |
`llrint` | [llrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`llround` | [llroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`log10` | [log10f](reference/log-logf-log10-log10f.md) | [log10](reference/log-logf-log10-log10f.md) | [log10l](reference/log-logf-log10-log10f.md) | - | - | - |
`log1p` | [log1pf](reference/log1p-log1pf-log1pl2.md) | [log1p](reference/log1p-log1pf-log1pl2.md) | [log1pl](reference/log1p-log1pf-log1pl2.md) | - | - | - |
`log2` | [log2f](reference/log2-log2f-log2l.md) | [log2](reference/log2-log2f-log2l.md) | [log2l](reference/log2-log2f-log2l.md) | - | - | - |
`logb` | [logbf](reference/logb-logbf-logbl-logb-logbf.md) | [logb](reference/logb-logbf-logbl-logb-logbf.md) | [logbl](reference/logb-logbf-logbl-logb-logbf.md) | - | - | - |
`lrint` | [lrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`lround` | [lroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`nearbyint` | [nearbyintf](reference/nearbyint-nearbyintf-nearbyintl1.md) | [nearbyint](reference/nearbyint-nearbyintf-nearbyintl1.md) | [nearbyintl](reference/nearbyint-nearbyintf-nearbyintl1.md) | - | - | - |
`nextafter` | [nextafterf](reference/nextafter-functions.md) | [nextafter](reference/nextafter-functions.md) | [nextafterl](reference/nextafter-functions.md) | - | - | - |
`nexttoward` | [nexttowardf](reference/nextafter-functions.md) | [nexttoward](reference/nextafter-functions.md) | [nexttowardl](reference/nextafter-functions.md) | - | - | - |
`remainder` | [remainderf](reference/remainder-remainderf-remainderl.md) | [剩下](reference/remainder-remainderf-remainderl.md) | [remainderl](reference/remainder-remainderf-remainderl.md) | - | - | - |
`remquo` | [remquof](reference/remquo-remquof-remquol.md) | [remquo](reference/remquo-remquof-remquol.md) | [remquol](reference/remquo-remquof-remquol.md) | - | - | - |
`rint` | [rintf](reference/rint-rintf-rintl.md) | [rint](reference/rint-rintf-rintl.md) | [rintl](reference/rint-rintf-rintl.md) | - | - | - |
`round` | [roundf](reference/round-roundf-roundl.md) | [圆满](reference/round-roundf-roundl.md) | [roundl](reference/round-roundf-roundl.md) | - | - | - |
`scalbln` | [scalblnf](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbln](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalblnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`scalbn` | [scalbnf](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbn](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`tgamma` | [tgammaf](reference/tgamma-tgammaf-tgammal.md) | [tgamma](reference/tgamma-tgammaf-tgammal.md) | [tgammal](reference/tgamma-tgammaf-tgammal.md) | - | - | - |
`trunc` | [truncf](reference/trunc-truncf-truncl.md) | [trunc](reference/trunc-truncf-truncl.md) | [truncl](reference/trunc-truncf-truncl.md) | - | - | - |
`carg` | - | - | - | [cargf](reference/carg-cargf-cargl.md) | [carg](reference/carg-cargf-cargl.md) | [cargl](reference/carg-cargf-cargl.md) |
`conj` | - | - | - | [conjf](reference/conj-conjf-conjl.md) | [conj](reference/conj-conjf-conjl.md) | [conjl](reference/conj-conjf-conjl.md) |
`creal` | - | - | - | [crealf](reference/creal-crealf-creall.md) | [creal](reference/creal-crealf-creall.md) | [creall](reference/creal-crealf-creall.md) |
`cimag` | - | - | - | [cimagf](reference/cimag-cimagf-cimagl.md) | [cimag](reference/cimag-cimagf-cimagl.md) | [cimagl](reference/cimag-cimagf-cimagl.md) |
`cproj` | - | - | - | [cprojf](reference/cproj-cprojf-cprojl.md) | [cproj](reference/cproj-cprojf-cprojl.md) | [cprojl](reference/cproj-cprojf-cprojl.md) |

## <a name="requirements"></a>要求

[std：需要 c + + 11](../build/reference/std-specify-language-standard-version.md) 或更高版本。

Windows SDK 10.0.20201.0 或更高版本。

## <a name="see-also"></a>另请参阅

[C 运行时库参考](c-run-time-library-reference.md)
