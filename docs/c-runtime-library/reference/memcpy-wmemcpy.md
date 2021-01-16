---
description: 了解详细信息： memcpy、wmemcpy
title: memcpy、wmemcpy
ms.date: 1/14/2021
api_name:
- memcpy
- wmemcpy
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: 49b08877f63bf0d331dcc40e2885b375fe6d1ee7
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243133"
---
# <a name="memcpy-wmemcpy"></a>`memcpy`, `wmemcpy`

在缓冲区之间复制字节。 提供这些函数的更多安全版本;请参阅[ `memcpy_s` 、 `wmemcpy_s` ](memcpy-s-wmemcpy-s.md)。

## <a name="syntax"></a>语法

```C
void *memcpy(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemcpy(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>参数

*`dest`*\
新缓冲区。

*`src`*\
从中进行复制操作的缓冲区。

*`count`*\
要复制的字符数。

## <a name="return-value"></a>返回值

的值 *`dest`* 。

## <a name="remarks"></a>注解

**`memcpy`** 将 *`count`* 字节从复制 *`src`* 到 *`dest`* ; **`wmemcpy`** 复制 *`count`* 宽字符 (两个字节) 。 如果源和目标重叠，则的行为 **`memcpy`** 是不确定的。 使用 **`memmove`** 处理重叠区域。

> [!IMPORTANT]
> 确保目标缓冲区等于或大于源缓冲区。 有关详细信息，请参阅 [避免缓冲区溢出](/windows/win32/SecBP/avoiding-buffer-overruns)。

> [!IMPORTANT]
> 由于如此多的缓冲区溢出，进而导致潜在的安全漏洞，因此， **`memcpy`** 其安全开发生命周期中的 "禁止" 函数列出了此函数 (SDL) 。  你可能会发现一些 VC + + 库类继续使用 **`memcpy`** 。  此外，您可能会发现 VC + + 编译器优化器有时会发出对的调用 **`memcpy`** 。  Visual C++ 产品的开发需符合 SDL 过程，因此对此禁止函数的使用进行了仔细评估。  在库使用情况下，已经对调用进行了仔细审查，确保通过这些调用不会产生缓冲区溢出。  对于编译器，某些代码模式有时会被识别为与的模式相同 **`memcpy`** ，因此会将其替换为对函数的调用。  在这种情况下，使用不 **`memcpy`** 比原始指令更安全; 它们只是经过优化，可以调用性能优化的 **`memcpy`** 函数。  正如使用 "safe" CRT 函数不保证安全性 (它们只是使其难以) ，使用 "禁止" 函数并不能保证危险 (只需进行更仔细的审查即可确保安全) 。
>
> 由于 **`memcpy`** VC + + 编译器和库的使用情况已经过仔细审查，因此在其他符合 SDL 的代码中，允许进行这些调用。  **`memcpy`** 应用程序源代码中引入的调用只有在安全专家审查了该使用时才符合 SDL。

**`memcpy`** **`wmemcpy`** 仅当在包含语句之前定义了常量，才能弃用和函数 **`_CRT_SECURE_DEPRECATE_MEMORY`** ，如以下示例中所示：

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

or

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`memcpy`**|`<memory.h>` 或 `<string.h>`|
|**`wmemcpy`**|`<wchar.h>`|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

[`memmove`](memmove-wmemmove.md)有关如何使用的示例，请参阅 **`memcpy`** 。

## <a name="see-also"></a>另请参阅

[缓冲区操作](../../c-runtime-library/buffer-manipulation.md)\
[`_memccpy`](memccpy.md)\
[`memchr`, `wmemchr`](memchr-wmemchr.md)\
[`memcmp`, `wmemcmp`](memcmp-wmemcmp.md)\
[`memmove`, `wmemmove`](memmove-wmemmove.md)\
[`memset`, `wmemset`](memset-wmemset.md)\
[`strcpy_s`, `wcscpy_s`, `_mbscpy_s`](strcpy-s-wcscpy-s-mbscpy-s.md)\
[`strncpy_s`, `_strncpy_s_l`, `wcsncpy_s`, `_wcsncpy_s_l`, `_mbsncpy_s`, `_mbsncpy_s_l`](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)\
