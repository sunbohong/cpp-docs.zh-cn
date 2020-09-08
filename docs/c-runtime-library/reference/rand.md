---
title: rand
description: 用于 rand 的 API 参考，它通过使用众所周知且完全可重现的算法生成一个伪随机数。
ms.date: 4/2/2020
api_name:
- rand
- _o_rand
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: 50c4f921c81ecad00abb19e6ce50158d450b170e
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555327"
---
# <a name="rand"></a>rand

使用众所周知且完全可重复的算法生成一个伪随机数。 提供此函数的更具编程的安全版本;请参阅 [rand_s](rand-s.md)。 **Rand**生成的数字不是加密安全的。 对于更安全的安全随机数生成，请使用 [rand_s](rand-s.md) 或在中的 c + + 标准库中声明的函数 [\<random>](../../standard-library/random.md) 。

## <a name="syntax"></a>语法

```C
int rand( void );
```

## <a name="return-value"></a>返回值

**rand** 返回伪随机数，如上所述。 无错误返回。

## <a name="remarks"></a>备注

**Rand**函数返回0到**RAND_MAX** (32767) 范围内的一个随机整数。 在调用**rand**之前，使用[srand](srand.md)函数对伪随机数生成器进行种子设定。

**Rand**函数生成一个众所周知的序列，它不适合用作加密函数。 对于更安全的安全随机数生成，请使用 [rand_s](rand-s.md) 或在中的 c + + 标准库中声明的函数 [\<random>](../../standard-library/random.md) 。 有关 **rand** 出错的信息以及如何处理 \<random> 这些缺点，请参阅此视频，该视频 [被视为有害](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful)。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**rand**|\<stdlib.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_rand.c
// This program seeds the random-number generator
// with the time, then exercises the rand function.
//

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

void SimpleRandDemo( int n )
{
   // Print n random numbers.
   int i;
   for( i = 0; i < n; i++ )
      printf( "  %6d\n", rand() );
}

void RangedRandDemo( int range_min, int range_max, int n )
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   int i;
   for ( i = 0; i < n; i++ )
   {
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min;
      printf( "  %6d\n", u);
   }
}

int main( void )
{
   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   SimpleRandDemo( 10 );
   printf("\n");
   RangedRandDemo( -100, 100, 10 );
}
```

```Output
22036
18330
11651
27464
18093
3284
11785
14686
11447
11285

   74
   48
   27
   65
   96
   64
   -5
  -42
  -55
   66
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
