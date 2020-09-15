---
title: realloc
description: 'Realloc 的 API 参考 ( # A1;这将重新分配内存块。'
ms.date: 9/11/2020
api_name:
- realloc
- _o_realloc
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _brealloc
- _nrealloc
- realloc
- _frealloc
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
ms.openlocfilehash: c68909b2f5d73959465d63af522ceeb00c8ce23e
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "90075811"
---
# <a name="realloc"></a>realloc

重新分配内存块。

## <a name="syntax"></a>语法

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>参数

*`memblock`*\
指向之前已分配内存块的指针。

*`size`*\
新大小（字节）。

## <a name="return-value"></a>返回值

**`realloc`** 返回指向重新 **`void`** 分配的 (的指针，并且可能已移动) 内存块。

如果没有足够的可用内存将块扩展到给定大小，则原始块将保持不变，并 **`NULL`** 返回。

如果 *`size`* 为零，则释放由指向的块 *`memblock`* ; 返回值为 **`NULL`** ，并 *`memblock`* 将其指向已释放的块。

返回值指向为任何类型的对象的存储适当对齐的存储空间。 若要获取指向类型而非的指针 **`void`** ，请在返回值上使用类型转换。

## <a name="remarks"></a>备注

> [!NOTE]
> **`realloc`** 尚未更新为实现 C17 行为，因为新行为与 Windows 操作系统不兼容。

**`realloc`** 函数更改已分配内存块的大小。 *`memblock`* 参数指向内存块的开头。 如果 *`memblock`* 为 **`NULL`** ， **`realloc`** 则的行为方式与 **`malloc`** 和分配新的字节块相同 *`size`* 。 如果不 *`memblock`* 为 **`NULL`** ，则它应为之前对、或的调用返回的指针 **`calloc`** **`malloc`** **`realloc`** 。

*`size`* 自变量提供块的新大小（以字节为单位）。 块的内容不随其新旧大小而更改，尽管新块可以在不同的位置。 由于新块可以在新的内存位置，因此，返回的指针 **`realloc`** 不一定是通过参数传递的指针 *`memblock`* 。 **`realloc`** 如果缓冲区增长，则不会为新分配的内存分配零。

**`realloc`****`errno`** **`ENOMEM`** 如果内存分配失败或请求的内存量超过，则将设置为 **`_HEAP_MAXREQ`** 。 有关此代码及其他错误代码的信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

**`realloc`** 调用以便 **`malloc`** 使用 c + + [_set_new_mode](set-new-mode.md) 函数设置新的处理程序模式。 新处理程序模式将指示是否在失败 **`malloc`** 时调用由 [_set_new_handler](set-new-handler.md)设置的新处理程序例程。 默认情况下， **`malloc`** 在无法分配内存时，不会调用新的处理程序例程。 您可以重写此默认行为，以便在 **`realloc`** 无法分配内存时， **`malloc`** 调用新的处理程序例程，其方式与 **`new`** 运算符在相同原因发生故障时相同。 若要重写默认值，请在程序的早期调用：

```C
_set_new_mode(1);
```

或链接到 NEWMODE.OBJ（请参阅[链接选项](../../c-runtime-library/link-options.md)）。

当应用程序与调试版的 C 运行时库链接时，将 **`realloc`** 解析为 [_realloc_dbg](realloc-dbg.md)。 有关在调试过程中如何托管堆的详细信息，请参阅 [CRT 调试堆](/visualstudio/debugger/crt-debug-heap-details)。

**`realloc`** 被标记为 `__declspec(noalias)` 和 `__declspec(restrict)` ，这意味着函数保证不修改全局变量，并且返回的指针没有化名。 有关详细信息，请参阅 [noalias](../../cpp/noalias.md) 和[限制](../../cpp/restrict.md)。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`realloc`**|\<stdlib.h> 和 \<malloc.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>另请参阅

[内存分配](../../c-runtime-library/memory-allocation.md)\
[calloc](calloc.md)\
[忙](free.md)\
[malloc](malloc.md)
