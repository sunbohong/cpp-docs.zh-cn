---
description: 了解详细信息： memmove、wmemmove
title: memmove、wmemmove
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 6f9942c232710585aa5837510f0f04e5db36fb2a
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243120"
---
# <a name="memmove-wmemmove"></a>`memmove`, `wmemmove`

将一个缓冲区移到另一个缓冲区。 提供这些函数的更多安全版本;请参阅[ `memmove_s` 、 `wmemmove_s` ](memmove-s-wmemmove-s.md)。

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

### <a name="parameters"></a>参数

*`dest`*\
目标对象。

*`src`*\
源对象。

*`count`*\
**`memmove`** 要复制的)  () 或 (字符数 **`wmemmove`** 。

## <a name="return-value"></a>返回值

的值 *`dest`* 。

## <a name="remarks"></a>注解

将 *`count`* (**`memmove`**) 或个字符 (**`wmemmove`**) 中的字节复制 *`src`* 到 *`dest`* 。 如果源区域的某些区域和目标重叠，则两个函数都可确保在重叠区域中的原始源字节被覆盖之前对其进行复制。

**安全说明** 确保目标缓冲区的大小等于或大于源缓冲区的大小。 有关详细信息，请参阅 [避免缓冲区溢出](/windows/win32/SecBP/avoiding-buffer-overruns)。

**`memmove`** **`wmemmove`** 仅当在包含语句之前定义了常量，才能弃用和函数 **`_CRT_SECURE_DEPRECATE_MEMORY`** ，如以下示例中所示：

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <string.h>
```

or

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`memmove`**|`<string.h>`|
|**`wmemmove`**|`<wchar.h>`|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

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

## <a name="see-also"></a>另请参阅

[缓冲区操作](../../c-runtime-library/buffer-manipulation.md)\
[`_memccpy`](memccpy.md)\
[`memcpy`, `wmemcpy`](memcpy-wmemcpy.md)\
[`strcpy`, `wcscpy`, `_mbscpy`](strcpy-wcscpy-mbscpy.md)\
[`strncpy`, `_strncpy_l`, `wcsncpy`, `_wcsncpy_l`, `_mbsncpy`, `_mbsncpy_l`](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)\
