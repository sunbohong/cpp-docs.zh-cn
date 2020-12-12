---
description: 了解详细信息： _malloc_dbg
title: _malloc_dbg
ms.date: 11/04/2016
api_name:
- _malloc_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- malloc_dbg
- _malloc_dbg
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
ms.openlocfilehash: 56b39ecbbe5f90d9eee378d4ce42016e5960ff63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299808"
---
# <a name="_malloc_dbg"></a>_malloc_dbg

在具有额外空间的堆中为调试标头和覆盖缓冲区分配内存块（仅限调试模式）。

## <a name="syntax"></a>语法

```C
void *_malloc_dbg(
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>parameters

*大小*<br/>
内存块的请求大小（以字节为单位）。

*blockType*<br/>
内存块的请求类型： **_CLIENT_BLOCK** 或 **_NORMAL_BLOCK**。

*filename*<br/>
指向请求分配操作的源文件名的指针或 **NULL**。

*linenumber*<br/>
请求分配操作所在的源文件中的行号或 **NULL**。

仅当已显式调用 **_malloc_dbg** 或已定义 [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)预处理器常量时， *filename* 和 *linenumber* 参数才可用。

## <a name="return-value"></a>返回值

成功完成后，此函数将返回指向分配的内存块的用户部分的指针、调用新的处理程序函数或返回 **NULL**。 有关返回行为的完整说明，请参阅以下“备注”部分。 有关如何使用新处理程序函数的详细信息，请参阅 [malloc](malloc.md) 函数。

## <a name="remarks"></a>备注

**_malloc_dbg** 是 [malloc](malloc.md) 函数的调试版本。 未定义 [_DEBUG](../../c-runtime-library/debug.md) 时，对 **_malloc_dbg** 的每次调用都会减少到对 **malloc** 的调用。 **Malloc** 和 **_malloc_dbg** 都在基堆中分配内存块，但 **_malloc_dbg** 提供多种调试功能：用于测试泄漏的块的用户部分两侧的缓冲区、用于跟踪特定分配类型的块类型参数，以及 / 用于确定分配请求的源的 filename *linenumber* 信息。

**_malloc_dbg** 分配内存块，其空间比请求的 *大小* 稍多。 其他空间将由调试堆管理器用于链接调试内存块，以及提供具有调试标头信息的应用程序和覆盖缓冲区。 分配该块后，使用值 0xCD 填充该块的用户部分，使用值 0xFD 填充每个覆盖缓冲区。

如果内存分配失败，或者如果所需的内存量 (包含之前提到) 的开销超过 **_HEAP_MAXREQ**， **_malloc_dbg** 将 **errno** 设置为 **ENOMEM** 。 有关此代码及其他错误代码的信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

若要了解如何在基堆的调试版本中分配、初始化和管理内存块，请参阅 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)。 有关分配块类型及其使用方式的信息，请参阅[调试堆上的块类型](/visualstudio/debugger/crt-debug-heap-details)。 有关在应用程序的调试版本中调用标准堆函数及其调试版本之间差异的信息，请参阅[堆分配函数的调试版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_malloc_dbg**|\<crtdbg.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

仅限 [C 运行时库](../../c-runtime-library/crt-library-features.md)的调试版本。

## <a name="example"></a>示例

有关如何使用 **_malloc_dbg** 的示例，请参阅 [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1)。

## <a name="see-also"></a>请参阅

[调试例程](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
