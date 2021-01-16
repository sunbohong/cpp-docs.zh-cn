---
description: 了解详细信息： memcmp、wmemcmp
title: memcmp、wmemcmp
ms.date: 1/14/2021
api_name:
- memcmp
- wmemcmp
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memcmp
- wmemcmp
helpviewer_keywords:
- wmemcmp function
- memcmp function
ms.assetid: 0c21c3e3-8ee4-40e5-add1-eb26d225fd8d
ms.openlocfilehash: 52f770cd2f5fee5c7d8e016682d80e81672588b8
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243146"
---
# <a name="memcmp-wmemcmp"></a>memcmp、wmemcmp

比较两个缓冲区中的字符。

## <a name="syntax"></a>语法

```C
int memcmp(
   const void *buffer1,
   const void *buffer2,
   size_t count
);
int wmemcmp(
   const wchar_t * buffer1,
   const wchar_t * buffer2,
   size_t count
);
```

### <a name="parameters"></a>参数

*buffer1*<br/>
第一个缓冲区。

*buffer2*<br/>
第二个缓冲区。

*计数*<br/>
要比较的字符数。  (比较 **wmemcmp**) 的 **memcmp**、宽字符的字节数。

## <a name="return-value"></a>返回值

返回值指示缓冲区之间的关系。

|返回值|Buf1 和 buf2 的第一个 *计数* 字符的关系|
|------------------|---------------------------------------------------------------|
|< 0|*buffer1* 小于 *buffer2*|
|0|*buffer1* 等同于 *buffer2*|
|> 0|*buffer1* 大于 *buffer2*|

## <a name="remarks"></a>注解

比较 *buffer1* 和 *buffer2* 的第一个 *计数* 字符并返回指示它们关系的值。 非零返回值的符号是缓冲区中的第一个不同值对之差的符号。 值被解释为 **`unsigned char`** 适用于 **memcmp** 和 **`wchar_t`** **wmemcmp** 的值。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**memcmp**|\<memory.h> 或 \<string.h>|
|**wmemcmp**|\<wchar.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

[C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。

## <a name="example"></a>示例

```C
// crt_memcmp.c
/* This program uses memcmp to compare
* the strings named first and second. If the first
* 19 bytes of the strings are equal, the program
* considers the strings to be equal.
*/

#include <string.h>
#include <stdio.h>

int main( void )
{
   char first[]  = "12345678901234567890";
   char second[] = "12345678901234567891";
   int int_arr1[] = {1,2,3,4};
   int int_arr2[] = {1,2,3,4};
   int result;

   printf( "Compare '%.19s' to '%.19s':\n", first, second );
   result = memcmp( first, second, 19 );
   if( result < 0 )
      printf( "First is less than second.\n" );
   else if( result == 0 )
      printf( "First is equal to second.\n" );
   else
      printf( "First is greater than second.\n" );

   printf( "Compare '%d,%d' to '%d,%d':\n", int_arr1[0], int_arr1[1], int_arr2[0], int_arr2[1]);
   result = memcmp( int_arr1, int_arr2, sizeof(int) * 2 );
   if( result < 0 )
      printf( "int_arr1 is less than int_arr2.\n" );
   else if( result == 0 )
      printf( "int_arr1 is equal to int_arr2.\n" );
   else
      printf( "int_arr1 is greater than int_arr2.\n" );
}
```

```Output
Compare '1234567890123456789' to '1234567890123456789':
First is equal to second.
Compare '1,2' to '1,2':
int_arr1 is equal to int_arr2.
```

## <a name="see-also"></a>另请参阅

[缓冲区操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr、wmemchr](memchr-wmemchr.md)<br/>
[memcpy、wmemcpy](memcpy-wmemcpy.md)<br/>
[memset、wmemset](memset-wmemset.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
