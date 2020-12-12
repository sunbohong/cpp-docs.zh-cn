---
description: 了解详细信息： memmove、wmemmove
title: memmove、wmemmove
ms.date: 11/04/2016
api_name:
- memmove
- wmemmove
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memmove
- wmemmove
helpviewer_keywords:
- wmemmove function
- memmove function
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
ms.openlocfilehash: 15dee8eab2a1b7eedd3891d8673647a711c0e499
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171382"
---
# <a name="memmove-wmemmove"></a>memmove、wmemmove

将一个缓冲区移到另一个缓冲区。 提供这些函数的更多安全版本；请参阅 [memmove_s、wmemmove_s](memmove-s-wmemmove-s.md)。

## <a name="syntax"></a>语法

```C
void *memmove(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemmove(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>parameters

*目的*<br/>
目标对象。

*src*<br/>
源对象。

*计数*<br/>
要 **复制 ()** 或多个字符 (**wmemmove**) 的字节数。

## <a name="return-value"></a>返回值

*Dest* 的值。

## <a name="remarks"></a>备注

将 *计数* 字节 (**memmove**) 或字符 (从 *src* 到 *目标* 的 **wmemmove**) 。 如果源区域的某些区域和目标重叠，则两个函数都可确保在重叠区域中的原始源字节被覆盖之前对其进行复制。

**安全说明** 确保目标缓冲区的大小等于或大于源缓冲区的大小。 有关详细信息，请参阅 [避免缓冲区溢出](/windows/win32/SecBP/avoiding-buffer-overruns)。

仅当在包含语句之前定义了常量 **_CRT_SECURE_DEPRECATE_MEMORY** （如以下示例中所示）时，才会弃用 **memmove** 和 **wmemmove** 函数：

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <string.h>
```

或

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**memmove**|\<string.h>|
|**wmemmove**|\<wchar.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_memcpy.c
// Illustrate overlapping copy: memmove
// always handles it correctly; memcpy may handle
// it correctly.
//

#include <memory.h>
#include <string.h>
#include <stdio.h>

char str1[7] = "aabbcc";

int main( void )
{
   printf( "The string: %s\n", str1 );
   memcpy( str1 + 2, str1, 4 );
   printf( "New string: %s\n", str1 );

   strcpy_s( str1, sizeof(str1), "aabbcc" );   // reset string

   printf( "The string: %s\n", str1 );
   memmove( str1 + 2, str1, 4 );
   printf( "New string: %s\n", str1 );
}
```

```Output
The string: aabbcc
New string: aaaabb
The string: aabbcc
New string: aaaabb
```

## <a name="see-also"></a>请参阅

[缓冲区操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy、wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
